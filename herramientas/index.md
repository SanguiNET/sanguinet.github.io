---
layout: article
title: "Herramientas para usar Telegram"
date: 2016-04-04T12:15:00-05:30
modified: 2016-04-04
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
share: false
---

Estos son los pasos básicos para instalar Telegram. También incluimos un anexo para funciones avanzadas.

{% include toc.html %}

## Instalación

Instalamos [Telegram](https://telegram.org/). El dispositivo que quiera instalar puede variar y te damos tres opciones:

A) Si instalas desde un móvil, sigue los pasos:

1. [Dírigete](https://telegram.org/dl) a la tienda de aplicaciones que corresponda.
2. Instala la aplicación. Necesitas tener espacio de almacenamiento suficiente.
3. Si tienes problemas de instalación. Omite los demás pasos y dígete a la opción C.
4. Abre la aplicación e inicia sesión.

B) Si instalas desde la PC, los pasos se asemejan un poco:

1. [Dírigete](https://desktop.telegram.org/) al portal Telegram Desktop.
2. Si usas Mac OS X instálalo desde la [tienda de aplicaciones de Apple](https://itunes.apple.com/us/app/telegram-desktop/id946399090). Omite los pasos 3 y 4.
3. Selecciona el instalador según el sistema operativo que llevas ejecutando en el equipo y descárgalo.
4. Ejecuta o descomprime el instalador (EXE para Windows, DMG para OS X, TAR para Linux).
5. Abre la aplicación e inicia sesión.

C) Si deseas por medio de un navegador web:
1. [Dírigete](https://web.telegram.org/) al portal Telegram Web.
2. Si usas Firefox, Chrome, Edge o alguno similar haz lo siguiente:
	 1. Ten a esa página web como acceso directo (puede estar en las opciones de la página).
	 2. Activa o concede que el sitio web pueda mostrar notificaciones.
	 3. Si fuera necesario también concede los permisos para tomar fotos o grabar audio (a tu criterio).
3. Incia sesión.

---

## Iniciando sesión

Para iniciar sesión basta con escoger tu número telefónico (o contratar con tu proveedor VoIP) y confirmar. Si no es la primera vez que inicias omite este paso.

>En algunos casos, Telegram necesita confirmar tu número telefónico en formato internacional. Asegúrate que tu celular puede recibir mensajes o llamadas con ese número. Contacta a tu proveedor de llamadas si ofrece algún cargo adicional.
>
>En caso que tengas problemas al recibir mensajes de confirmación contacta al equipo en [esta sección](#Problemas en mensajes de confirmación)
{% highlight text %}
Telegram Code: 12345
{% endhighlight %}

---

## Problemas en mensajes de confirmación
Si tienes problemas para recibir mensajes de texto o llamadas ingresa a [esta página](https://telegram.org/support) o [vía DM en Twitter](https://twitter.com/smstelegram).
Aunque el equipo puede audarte en español, te recomendamos seguir el formato en inglés como este:

{% highlight text %}
Help. I don't login in Telegram.
My Telephone: +XX YYYYYYYYY
My OS client: ZZZZZ
{% endhighlight %}

Siendo ''Telephone'' el número telefónico y ''OS Client'' el sistema operativo donde estabas usando (Windows, Android...).

---

## Primeros pasos

### Abrir un chat, grupo o canal

Para abrir una conversación con tus cercados dirígete en la sección Contactos (varía según sistema oprerativo). En caso que quieras hacer un chat grupal puedes recurrir una conversación hasta 5000 miembros. Los grupos pueden mejorarse para hacerlo públicos y almacenarlos en la nube. Para los que quieren mandar posts a modo de blog puedes usar los canales y compartir a los contactos o mediante enlace.

### Los contactos

Los contactos son el medio escencial para comunicarte Telegram.

* Añadir: Para añadir basta agregar a tu libreta de contactos y sicronizarlo.
* Notificar si el nuevo usuario usa Telegram: Eso se puede desactivar en los ajustes de Android y escritorio.
* Alias: También es posible conversar a otros usuarios mediante alias, sin necesidad de revelar su propio número.
* Eliminar usuarios: Si deseas borrar a cada contacto y dirigir al menú contextual > Eliminar ([fuente](http://technology.onehowto.com/article/how-to-delete-a-telegram-contact-1472.html)).

### Tipos de envío

En Telegram se puede envíar imágenes, videos o mensajes de audio. También se puede envíar canciones, ubicaciones geográficas y archivos (como documentos) hasta 1.5 GB. 

### Bots integrales

Además, puedes emplear los bots para hacer amenas las conversaciones. Puedes compartir un GIF, un mensaje estilizado, un videoclip, entre otros. Entre los más principales son @bold (usando Markdown), @gif (Giphy), @vid (Youtube), @wiki (Wikipedia), entre otros ([fuente](https://core.telegram.org/bots/inline)).

## Mi cuenta de usuario

A grosso modo, tu cuenta de Telegram se compone de (sin orden relevante):

{% highlight bash %}
Mi ID
├── Nombre                              # Incluye apellidos o nombre de entidades.
├── Número                              # Número telefónico (privado)
├── Código ID                           # Código ID de usuario (para identificarte)
├── Mis conversaciones
|    ├── Chats normales                 # Conversaciones almacenadas en la nube con la ID.
|    ├── Chats secretos		            # Conversaciones privadas (almacenadas en el teléfono).
├── Grupos                              # Tanto los grupos propios como los grupos que participas (funciona por separado).
|    ├── Grupos                         # Conversaciones con almacenamiento local.
|    ├── Supergrupos                    # Conversaciones almacenadas en la nube pensado en conversaciones públicas.
├── Canales                             # Las "listas de difusión" que son almacendas en la nube (funciona por separado).
├── Bots                                # Usuarios que sirven de mayordomos para el Internet de las Cosas.
{% endhighlight %}

## Más información

Si quieres aportar sugerencias a la página [envía una consulta](https://github.com/Niaj-scio/niaj-scio.github.io/issues) en GitHub. Los problemas son arreglados sólo para el sitio web.

En caso que tengas dudas puedes consultar la **[sección de preguntas frecuentes](https://telegram.org/faq/es)** o hacer una consulta en Ayuda > Hacer una pregunta.

### Canales afines
Para los que estén informados sobre las características de Telegram, te ofrecemos:

* [Telegram News](https://telegram.me/newschannel), canal de publicación en inglés.
* [Telegram News](https://telegram.me/tnews_ru), canal ruso de la comunidad en VK.
* [tlgram.net Noticias](https://telegram.me/tlgramNET), canal en español sobre noticias y análisis.
* [Chatfuel News](https://telegram.me/chatfuel), canal del administrador de bots de Telegram.

Canales cercanos y/o oficiales:

* [Telegram Challenge](https://telegram.me/durovschallenge), canal del proyecto experimental promovido por Dúrov.
* [Telegram Desktop](https://telegram.me/desktop), canal del cliente para escritorio.
* [BotNews](https://telegram.me/BotNews), canal oficial para el desarrollo de bots .
* [Canal de Telegram](https://telegram.me/telegram), canal principal.

---

## Licencia

Los clientes de Telegram están bajo la licencia GPL.
