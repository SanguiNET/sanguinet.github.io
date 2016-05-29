# Sitio web del proyecto Niaj-scio

Este es el proyecto Niaj-scio. Es algo informativo y etretenido para los que quieren aprender en Telegram. Hemos creado el portal con el fin de impulsar el desarrollo de la mensajería mencionada.

Su funcionamiento es fácil. La información lo hacemos de la forma más práctica posible. Solo necesitas un editor de texto si quieres mejorar.

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
		* "Directorio", página recopilatoria de cananles y bots (se puede vincular los artículos si es posible)
	* "About", sobre el portal web (casi análogo a este Léame)
	* "Terms" o [página de términos](http://niaj-scio.github.io/terms/), incluido una cláusula de responsabilida limitada (oculto)
* Los accesorios de la página
	* "images" para las imágenes del sitio, recomendamos usar la menor cantidad de imágenes posible
	* "\_data" carpeta para el encabezado, pie de página y la barra de navegación
	* "\_layouts" carpeta donde se preformatea el blog. Allí está home.html para la página principal
* Archivos preconfigurados
	* "\_templates", carpeta para estilos predeterminados en las páginas del sitio
	* "atom.txt", para el canal RSS
	* "\_config", configuración del sitio
	* "index.md"
		*En la raíz para la página con texto modificable, no confuir con home.html para el código Ruby
		*En las carpetas como "Articles" es el directorio URL antes de acceder al arículo
		
## Características del blog

![screenshot of Skinny Bones](http://mmistakes.github.io/skinny-bones-jekyll/images/skinny-bones-theme-feature.jpg)

* Usa Jekyll 3.x y es compatible con GitHub Pages;
* Al usar un estilo de página dinámica sin base de datos la carga es "instantánea";
* Estilos de cascada con Sass;
* Uso de carpetas "articles" y "media" para crear artículos y multimedia:
	* Edición rápida con [YAML y Markdown](http://push.cwcon.org/learn/yaml-and-markdown.html);
	* Categorías, etiquetas y tabla de contenidos (opcional);
	* Soporte de encabezado y pie de página. Tabla de información del autor;
	* Por favor, use la página "2016-03-29-muestra.md" como muestra para el uso de Markdown;
* Complementos externos: Disqus, , social sharing links, and Google AdSense ads;
* Licencia de código abierto (ver "terms");
* No requiere usar .htaccess en Github Pages por motivos de seguridad;
* Y falta más.

## Cómo mejorar Niaj-scio

Recuerde que Niaj-scio está pensado en Telegram. Si deseas añadir trucos para potenciar Telegram o integrar servicios externos, eres bienvenido.

### Instalar una copia en la PC
Para iniciar una copia del blog en la PC:

1. Ejecuta Ruby en tu navegador
	* Usando [Bitnami](https://bitnami.com/stack/ruby) (recomendado):
		1. Visita la [página de descargas](https://bitnami.com/stack/ruby/installer)
		2. Descárgalo e instálalo.
	* Usando [Rubyinstaller](http://rubyinstaller.org/):
		1. Revisa la [página de ayuda](https://github.com/oneclick/rubyinstaller/wiki/faq), en inglés.
		2. Instálalo.
	* De la forma clásica (es opcional):
		1. Instala un web server usando XAMPP.
		2. Programa el servidor para ejecutar Ruby on Rails (el paso es bastante extenso).
2. Ejecuta el panel de control o la línea de comandos
	* Para Bitnami
		1. Ejecuta use_ruby.bat (en el caso de Windows)
		2. Ejecuta los comandos ([guia rápida](https://github.com/jekyll/jekyll/issues/3191 y en la carpeta extras).
		3. Tu carpeta será creada como "my-awesome-site", depende del nombre que hayas asignado.
3. Descomprime una copia del portal y muévelo hacia la carpeta "my-awesome-site".
	* Para otros servicios
		1. Comprueba si tienes los permisos root para la línea de comandos.
		2. Ejecuta los comandos ([guia rápida](https://github.com/jekyll/jekyll/issues/3191) e info en la carpeta extras).
		3. Tu carpeta será creada como "my-awesome-site", depende del nombre que hayas asignado.
4. Comprueba si está listo:
	* Si todo está incorporado, como en el caso de Bitnami, no necesitas configurar el módulo Apache o conectar la base de datos.
	* Si no encuentras las "gemas" al ejecutar el blog, puedes consultar el sitio web de [Jekyll](https://jekyllrb.com/).
	* Revisa la lista de gemas solicitadas en el archivo "_config.yml".

### Aportar un artículo
Para crear o modificar un documento:

1. Consulta el archivo markdown.html, escrito por Joe Di Castro, para formatear texto.
2. Revisa el contenido del blog
	* Para "terms" y "tutorial", puedes editar la páginas correspondientes.
	* Para carpetas como "Articles" y "Media" puedes:
		* Crear un artículo llamado "mitítulo.md"
		* Modificar un artículo .md
3. ¡Usa un editor de texto y redacta tu artículo!
	* Opcionalmente, usa el editor de texto [Stackedit](https://stackedit.io/editor) para previsualizar en línea
### SEO
Si sientes que hay problemas SEO revisa la documentación debajo:
* http://veithen.github.io/2014/11/17/jekyll-schema-org-metadata.html
* http://jekyll.tips/tutorials/seo/
* http://cesalberca.es/seo-con-jekyll