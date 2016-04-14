# Sitio web del proyecto Niaj-scio

Este es el proyecto Niaj-scio. Es algo informativo y etretenido para los que quieren aprender en Telegram. Queremos impulsar el desarrollo la mensajería mencionada de la forma más práctica posible.

Está basado en Jekyll con el tema [Skinny Bonnes](https://github.com/Niaj-scio/skinny-bones-jekyll) con variaciones. Para ver el portal en la PC sin Internet revisa la documentación más abajo.

Por el momento esta página está en idioma español. Pueden añadir aportes para crecer el portal. Más información se añadirá a su momento.

---

## Qué contiene el blog
Los artículos de niaj-scio.github.io están organizados en:

* Las páginas y carpetas
	* "Herramientas", página relacionada a Telegram y primeros pasos
	* "Posts", carpeta de noticias
		* "Articles" o "artículos", carpeta de artículos sobre Telegram
		* "Media", carpeta de videos y archivos multimedia, éstos deben enlazarse a un portal externo como YouTube o Vimeo
	* "About", sobre el portal web (casi análogo a este Léame)
	* "Terms" o [página de términos](http://niaj-scio.github.io/terms/), incluido una cláusula de responsabilida limitada
* Los accesorios de la página
	* "images" para las imágenes del sitio, recomendamos usar la menor cantidad de imágenes posible
	* "\_data" carpeta para el encabezado y pie de página, la página completa es generada en código Ruby
	* "\_layouts" carpeta donde se ubica home.html para la página principal
* Archivos preconfigurados
	* "\_templates", carpeta para estilos predeterminados en las páginas del sitio
	* "atom.txt", para el canal RSS
	* "\_config", configuración del sitio
	* "index.md"
		*En la raíz se usa como barra lateral, no confuir con home.html de "\_layouts"
		*En las carpetas como "Articles" es el directorio URL antes de acceder al arículo
## Características del blog

![screenshot of Skinny Bones](http://mmistakes.github.io/skinny-bones-jekyll/images/skinny-bones-theme-feature.jpg)

* Usa Jekyll 3.x y es compatible con GitHub Pages.
* Al usar un estilo de página dinámica sin base de datos la carga es "instantánea".
* Estilos de cascada con Sass.
* Uso de carpetas "articles" y "media" para crear artículos y multimedia.
	* Edición rápida con [YAML y Markdown](http://push.cwcon.org/learn/yaml-and-markdown.html).
	* Categorías, etiquetas y tabla de contenidos (opcional).
	* Soporte de encabezado y pie de página. Tabla de información del autor.
	* Por favor, use la página "2016-03-29-muestra.md" como muestra para el uso de Markdown.
* Complementos externos: Disqus, , social sharing links, and Google AdSense ads.
* Licencia de código abierto (ver "terms")
* Y falta más.

## Cómo añadir un artículo para Niaj-scio

Recuerde que Niaj-scio está pensado en Telegram. Si deseas añadir trucos para potenciar Telegram o integrar servicios externos, eres bienvenido.

Para iniciar una copia del blog en la PC:

1. Ejecuta Ruby en tu navegador
	* De la forma clásica
		1. Instala un web server.
		2. Alista el lenguaje Ruby on Rails. El programa es desición de cada uno.
	* De la forma más fácil. En este caso puedes usar [Rubyinstaller](http://rubyinstaller.org/). 
		1. Revisa la [página de ayuda](https://github.com/oneclick/rubyinstaller/wiki/faq), en inglés.
		2. Instálalo.
2. Descomprime una copia del portal y muévelo hacia el servidor web.
3. Todo está incorporado. No requiere configurar o conectar la base de datos.
4. Si tienes errores al descomprimir el blog, puedes consultar el sitio web de [Jekyll](https://jekyllrb.com/).

Para crear o modificar un documento:

1. Consulta el archivo markdown.html, escrito por Joe Di Castro, para formatear texto.
2. Revisa el contenido del blog
	* Para "terms" y "herramientas", puedes editar la páginas correspondientes.
	* Para carpetas como "Articles" y "Media" puedes:
		* Crear un artículo llamado "mitítulo.md"
		* Modificar un artículo .md
3. ¡Usa un editor de texto y redacta tu artículo!