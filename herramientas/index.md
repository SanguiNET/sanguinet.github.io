---
layout: article
title: "Getting Started with Skinny Bones"
date: 2014-06-25T13:57:25-04:00
modified: 2016-01-19
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
2.1. Ten a esa página web como acceso directo (puede estar en las opciones de la página).
2.2. Activa o concede que el sitio web pueda mostrar notificaciones.
2.3. Si fuera necesario también concede los permisos para tomar fotos o grabar audio (a tu criterio).
3. Incia sesión.

---

## Iniciando sesión

Para iniciar sesión basta con escoger tu número telefónico (o contratar con tu proveedor VoIP) y confirmar. Si no es la primera vez que inicias omite este paso.

>En algunos casos, Telegram necesita confirmar tu número telefónico en formato internacional. Asegúrate que tu celular puede recibir mensajes o llamadas con ese número. Contacta a tu proveedor de llamadas si ofrece algún cargo adicional.
>
>En caso que tengas problemas al recibir mensajes de confirmación contacta al equipo en [esta sección](#Problemas en formación d)
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
### Site Wide Configuration

`_config.yml` is your friend. Open it up and personalize it. Most variables are self explanatory but here's an explanation of each anyways:

#### Site Title

The title of your site... shocker!

Example `title: Skinny Bones`

#### Site Description

A description of your site. Used in page meta.

Example `description: "A lightweight site starter for Jekyll"`

#### Site Logo

Site logo, used mostly as a default image that appears on Twitter Cards if a large feature image isn't present. If used place a square image around 120 x 120 pixels in `/images/`.

Example `logo: 120x120.gif`

<figure>
  <img src="{{ site.url }}/images/twitter-card-screenshot.jpg" alt="sample Twitter Card screenshot">
  <figcaption>Site logo is used for Twitter Cards when a feature image is not defined for the page.</figcaption>
</figure>


[^protocol]: If you decide to use a protocol-relative URL know that it will most likely break sitemap.xml that the Jekyll-Sitemap gem creates. If a valid sitemap matters to you I'd suggest [creating your own sitemap.xml](http://davidensinger.com/2013/03/generating-a-sitemap-in-jekyll-without-a-plugin/) and apply some Liquid logic to prepend links to posts/pages with `https:`.

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
├── Grupos                              # Tanto los grupos propios como 
|    ├── Grupos                         # Conversaciones con almacenamiento local.
|    ├── Supergrupos                    # Conversaciones almacenadas en la nube pensado en conversaciones públicas.
├── Canales                             # Las "listas de difusión" que son almacendas en la nube.
├── Bots                                # Usuarios que sirven de mayordomos para el Internet de las Cosas.
{% endhighlight %}

## Más información

Si quieres aportar sugerencias a la página [envía una consulta](https://github.com/Niaj-scio/niaj-scio.github.io/issues) en GitHub. Los problemas son arreglados sólo para el sitio web.

En caso que quieras dar **sugerencias a Telegram** dirígete a Ayuda > Hacer una pregunta.

---

## Licencia

Los clientes de Telegram están bajo la licencia GPL.
