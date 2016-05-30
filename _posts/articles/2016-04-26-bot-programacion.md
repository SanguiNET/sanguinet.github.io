---
layout: article
title: "Cómo hacer un bot"
categories: articles
modified: 2016-04-26T12:06:11-05:30
tags: [inicio]
comments: true
ads: true
share: true
---

Un bot es un complemento para enriquecer las conversaciones. Dichas conversaciones reducen el tiempo necesario para realizar consultas vía conversación, administrar grupos, usar botones interactivos, etcétera.
Para crear un bot es necesario que conozcas su funcionamiento y debes pedir una autorización para funcionar.

### Ejemplos para inspirarte

* Integración con otros servicios: Puedes gestionar Twitter desde la conversación del bot
* Sistemas de alertas: Noticias de varias fuentes (y compartir por los canales), el clima, desastres naturales, etcétera.
* Juegos: Adivinanzas, ajedrez, ludo y más. 
* Servicios de integración social: Citas, conversaciones por lugar, preguntas y respuestas.
* Marketing: Si dominas un poco más, los teclados integrados permiten cambiar la lista de productos, comprar o compartir.
* Administración de grupos: Moderar los mensajes, restringir stickers, ver estadísticas, widgets para páginas web.

Recuerda: [Visita el directorio para revisar algunos servicios en acción](http://niaj-scio.github.io/directorio)

### Requisitos

* Una cuenta de usuario activa (puedes hacer una aparte)
* Programar el código desde un servidor
	* Si piensas usar tu propio servidor te recomendamos hacer desde una computadora preparada.
	* Te sugerimos usar Linux para agilizar con línea de comandos, una tarjeta RAM de mayor capacidad, disco duro de mayor velocidad y una fuente de poder de alta eficiencia.
* Un gestor de datos SQL o MariaDB. No es necesario usar base de datos cuando quieras iniciar con "hola mundo".

Algunas condiciones:

* Los bots no tienen estado de conexión ni marcas de visto.
* Los bots tienen almacenamiento limitado y no son conservados en la nube sino en el servidor por cuenta propia.
* Los bots no pueden iniciar conversaciones (necesitan el comando /start)
* Los bots tienen un alias acabado en "bot".
* Los bots en los grupos no reciben todos los mensajes por defecto (modo privado).
* Si son administradores, el modo privado está desactivado.

### Pedir permiso

Para usar los bots es indispensable pedir un permiso al **botfather**.

1. Ingresa a Telegram con el alias [@botfather](http://telegram.me/botfather).
2. Inicia (con el botón Iniciar o ejecutando "/start").
3. Este bot usa comandos lineales. El primero que debes hacer es enviar el comando "/newbot" (sin comillas).
4. Escribes el nombre del bot y su alias (por defecto, casabot).
5. Al crear tu bot, tendrás una clave para integrar con tu servidor (lo verás en el siguiente paso).
6. Para dar estilo a tu bot, prueba con otros comandos:
	* "/setdescription": para la descripción de bienvenida. Estará debajo de "¿Qué puede hacer este bot?".
	* "/setabouttext": es un "acerca de", se encuentra en el perfil y puedes añadir un soporte técnico.
	* "/setuserpic": la foto del bot para identificarlo mejor.

### Configuración

Hay varias maneras de configurar un bot al servidor. Eso depende de la capacidad que le darás a tu bot y la base de datos.

* Puedes usar las líneas de comandos. Algunos tienen un archivo preconfigurado para instalar fácilmente.
* Si no tienes un servidor propio, puedes conseguir desde la [consola de Google Engine](https://console.developers.google.com/project).
* Usa el tóken (o clave) para conectar con la plataforma y ejecutar en las conversaciones.
* Existe varios métodos de respuesta en los bots con getUpdates y setWebhook. Se diferencia por el protocolo HTTPS y su mecanismo de autenticación.

### Hola mundo

Para que veas un bot en acción, empieza a crear tu "hola mundo". Este bot se realizó en un sólo fichero PHP que muestra sólo el mensaje. El código fuente original está en [JNEEN](http://rouge.jneen.net/pastes/ZDJw).
Para probar, una vez configurado en tu servidor, basta ir al boton "Inciar" o el comando "/start". 

{% highlight php %}
<?php

//Definimos el tocken y la url de Telegram
define('BOT_TOKEN', '12345678:replace-me-with-real-token');
define('API_URL', 'https://api.telegram.org/bot'.BOT_TOKEN.'/');

//Hacemos una consulta Webhook
function apiRequestWebhook($method, $parameters) {
  if (!is_string($method)) {
    error_log("Method name must be a string\n");
    return false;
  }

  //Añadimos los parámetros
  if (!$parameters) {
    $parameters = array();
  } else if (!is_array($parameters)) {
    error_log("Parameters must be an array\n");
    return false;
  }

  $parameters["method"] = $method;

  header("Content-Type: application/json");
  echo json_encode($parameters);
  return true;
}

function exec_curl_request($handle) {
  $response = curl_exec($handle);

  if ($response === false) {
    $errno = curl_errno($handle);
    $error = curl_error($handle);
    error_log("Curl returned error $errno: $error\n");
    curl_close($handle);
    return false;
  }

  $http_code = intval(curl_getinfo($handle, CURLINFO_HTTP_CODE));
  curl_close($handle);

  //Definimos un error 500 para evitar denegación de acceso
  if ($http_code >= 500) {
    sleep(10);
    return false;
  } else if ($http_code != 200) {
    $response = json_decode($response, true);
    error_log("Request has failed with error {$response['error_code']}: {$response['description']}\n");
    if ($http_code == 401) {
      throw new Exception('Invalid access token provided');
    }
    return false;
  } else {
    $response = json_decode($response, true);
    if (isset($response['description'])) {
      error_log("Request was successfull: {$response['description']}\n");
    }
    $response = $response['result'];
  }

  return $response;
}

//Consultamos los parámetros
function apiRequest($method, $parameters) {
  if (!is_string($method)) {
    error_log("Method name must be a string\n");
    return false;
  }

  if (!$parameters) {
    $parameters = array();
  } else if (!is_array($parameters)) {
    error_log("Parameters must be an array\n");
    return false;
  }

  foreach ($parameters as $key => &$val) {
    // codificando a un parámetro array JSON, por ejemplo reply_markup
    if (!is_numeric($val) && !is_string($val)) {
      $val = json_encode($val);
    }
  }
  $url = API_URL.$method.'?'.http_build_query($parameters);

  $handle = curl_init($url);
  curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);
  curl_setopt($handle, CURLOPT_CONNECTTIMEOUT, 5);
  curl_setopt($handle, CURLOPT_TIMEOUT, 60);

  return exec_curl_request($handle);
}

function apiRequestJson($method, $parameters) {
  if (!is_string($method)) {
    error_log("Method name must be a string\n");
    return false;
  }

  if (!$parameters) {
    $parameters = array();
  } else if (!is_array($parameters)) {
    error_log("Parameters must be an array\n");
    return false;
  }

  $parameters["method"] = $method;

  $handle = curl_init(API_URL);
  curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);
  curl_setopt($handle, CURLOPT_CONNECTTIMEOUT, 5);
  curl_setopt($handle, CURLOPT_TIMEOUT, 60);
  curl_setopt($handle, CURLOPT_POSTFIELDS, json_encode($parameters));
  curl_setopt($handle, CURLOPT_HTTPHEADER, array("Content-Type: application/json"));

  return exec_curl_request($handle);
}

function processMessage($message) {
  // procesar mensaje de entrada
  $message_id = $message['message_id'];
  $chat_id = $message['chat']['id'];
  if (isset($message['text'])) {
    // incoming text message
    $text = $message['text'];

    if (strpos($text, "/start") === 0) {
      apiRequestJson("sendMessage", array('chat_id' => $chat_id, "text" => 'Hello', 'reply_markup' => array(
        'keyboard' => array(array('Hello', 'Hi')),
        'one_time_keyboard' => true,
        'resize_keyboard' => true)));
    } else if ($text === "Hello" || $text === "Hi") {
      apiRequest("sendMessage", array('chat_id' => $chat_id, "text" => 'Nice to meet you'));
    } else if (strpos($text, "/stop") === 0) {
      // stop now
    } else {
      apiRequestWebhook("sendMessage", array('chat_id' => $chat_id, "reply_to_message_id" => $message_id, "text" => 'Cool'));
    }
  } else {
    apiRequest("sendMessage", array('chat_id' => $chat_id, "text" => 'I understand only text messages'));
  }
}

//usando enlaces secretos para que lea sólo el servidor
define('WEBHOOK_URL', 'https://my-site.example.com/secret-path-for-webhooks/');

if (php_sapi_name() == 'cli') {
  // if run from console, set or delete webhook
  apiRequest('setWebhook', array('url' => isset($argv[1]) && $argv[1] == 'delete' ? '' : WEBHOOK_URL));
  exit;
}

$content = file_get_contents("php://input");
$update = json_decode($content, true);

if (!$update) {
  // si recibe un mensaje de error, este no avisa
  exit;
}

if (isset($update["message"])) {
  processMessage($update["message"]);
}
{% endhighlight %}

### Usar librerías

Una vez que entiendas el hola mundo, te será familiar el mecanismo del API para Telegram. Como dato adicional, si quieres usar un lenguaje de programación a tu gusto, te ofrecemos una librería de implementación. Para instalar basta ir a los repositorios de Github mostrados abajo:

* [C# de MrRoundRobin](https://github.com/MrRoundRobin/telegram.bot)
* [C++ del usuario de Reddit FloodCode](https://github.com/reo7sp/tgbot-cpp/issues) 
* [Java por Zack Pollard](https://github.com/zackpollard/JavaTelegramBot-API)
* [Go de Syfaro](https://github.com/go-telegram-bot-api/telegram-bot-api)
* [NodeJS de Suppen](https://github.com/Suppen/Telegram-API-wrapper-for-JS)
* [PHP de Avtandil Kikabidze](https://github.com/akalongman/php-telegram-bot)
* [Python de yukuku](https://github.com/yukuku/telebot)
* [Wrapper para Scala](https://github.com/mukel/telegrambot4s)
* [Yii Framework](https://github.com/iamraccoon/Go-Offline-Telegram-Bot)

Nota: Es posible que algunas implementaciones no funcionen bien por cambios en la API de la plataforma. Puedes ver la [lista completa en Reddit](https://www.reddit.com/r/TelegramBots/comments/3bsec7/unofficial_collection_of_api_wrappers/).

### Soporte técnico

Por ahora si tienes alguna duda puedes consultar al soporte técnico por [@BotSupport](https://telegram.me/botsupport).

### Fuentes

* [Androcastellano](http://androcastellano.com/telegram-3-0-anade-bots-crea-el-tuyo-con-nuestro-tutorial/)
* [GenBeta](http://www.genbetadev.com/desarrollo-aplicaciones-moviles/creando-un-bot-con-el-api-de-telegram-i)
* [Documentación oficial de Bot API](https://core.telegram.org/bots/api)
* [Preguntas frecuentes](https://core.telegram.org/bots/faq)
* [Geekteory](https://geekytheory.com/telegram-programando-un-bot-en-python/)