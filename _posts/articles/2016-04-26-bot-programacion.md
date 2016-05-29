---
layout: article
title: "Cómo hacer un bot"
categories: articles
modified: 2016-04-26T12:06:11-05:30
tags: [inicio]
comments: true
ads: true
draft: true
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
* Un gestor de datos

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
2. Inicia (con el botón Iniciar).
3. Aquí inicias escribiendo comandos. El primero es "/newbot".
4. Escribes el nombre del bot y su alias.
5. Al crera tu bot, tendrás una clave para integrar con tu servidor.
6. Siguiendo con los comandos, algunos más permiten describir mejor a tu bot:
	* "/setdescription": para la descripción de bienvenida. Estará debajo de "¿Qué puede hacer este bot?".
	* "/setabouttext": es un "acerca de", se encuentra en el perfil y puedes añadir un soporte técnico.
	* "/setuserpic": la foto del bot para identificarlo mejor.

### Usar librerías

Si deseas programar un bot, según el lenguaje de programación a tu gusto, te ofrecemos una librería de implementación. Para ahorrarte tiempo en instalar y actualizar, los enlaces son de Github.

* [C# de MrRoundRobin](https://github.com/MrRoundRobin/telegram.bot)
* [C++ del usuario de Reddit FloodCode](https://github.com/reo7sp/tgbot-cpp/issues) 
* [Go de Syfaro](https://github.com/go-telegram-bot-api/telegram-bot-api)
* [NodeJS de Suppen](https://github.com/Suppen/Telegram-API-wrapper-for-JS)
* [PHP de Avtandil Kikabidze](https://github.com/akalongman/php-telegram-bot)
* [Python de yukuku](https://github.com/yukuku/telebot)
* [Wrapper para Scala](https://github.com/mukel/telegrambot4s)

Nota: Es posible que algunas implementaciones no funcionen bien por cambios en la API de la plataforma. Puedes ver la [lista completa en Reddit](https://www.reddit.com/r/TelegramBots/comments/3bsec7/unofficial_collection_of_api_wrappers/).

### Configuración

Hay varias maneras de configurar un bot al servidor. Puedes usar las líneas de comandos. Si no tienen un servidor propio, puedes conseguir desde la [consola de Google Engine](https://console.developers.google.com/project).

### Fuentes

* [Androcastellano](http://androcastellano.com/telegram-3-0-anade-bots-crea-el-tuyo-con-nuestro-tutorial/)
* [GenBeta](http://www.genbetadev.com/desarrollo-aplicaciones-moviles/creando-un-bot-con-el-api-de-telegram-i)