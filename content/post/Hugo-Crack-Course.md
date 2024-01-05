+++
title = 'Hugo Crack Course'
date = 2024-01-03T13:48:25+01:00
draft = false
tags = [
    'hugo',
    'courses',
    'blog'
]
+++

# Introduccion

*tmcyb3r.com* 

`History of Build of tmcyb3r.com`

Fui un `Jekill` desde siempre, un dia me puse testear hugo y probandolo en localhost me ha gustado, quise empezar el año y darle otro color, de hugo puedo decir que mas me gusta es el minimalismo, y tmb el modus-operandi es `cool`, decidi no migrar mi blog, y partir desde `0` , con hugo.


Despues de ver cientos de posts y articulos en internet ninguno de ellos no me han servido (desactualizados o incorrectos) en cuanto a mis propositos. Tenia en mis planos Github Pages + Cloudflare.

Queria levantar el blog, alojarlo en github pages obviamente, ademas de ello conectarlo/alojarlo en cloudflare (gratis) + (seguridad+dominio+spam+reglas+firewall) mas el dominio personalizado (para ello compre el dominio de cloudflare directamente, mas que recomendado).

# Requirements

Para empezar necesitamos:

* Hugo and Git software (esto es diferente si estas en linux o en windows)
* Github account (free o de pago, es indiferente)
* Cloudflare account (free)
* Domain name (no obligatorio, pero recomendado, cloudflare te asigna uno gratis: tmcyb3r.pages.dev)
* Ganas de aprender y mucha paciencia :) no todo va ser next,next ;)

# Install Software

Necesitamos hugo y git instalados: (en mi caso en `arch` uso `yay` es mi preferido, si estas en debian te sonara `sudo apt`, y en mac `brew install hugo`, y para windows usa WSL y choco, aunque hay otros)

```
yay -S hugo  #te instala la ultima version, en arch siempre tenemos lo ultimo :) eso si
```

Comprueba hugo:
```
hugo version  #a dia de hoy estaba en v0.121.1 esto es importante ya veras porque;)
```

# Hugo

### Creating a new Site Blog

Abre tu terminal, consola, yo uso `kitty` el gatito;;):

```
cd ~/myblog
hugo new site myblog
cd /myblog
```
Listo, en tan solo unos seg. hugo creara un blog/site y veras una multitud de folders/carpetas y archivos, pero chill, ya entenderas.

No hagas nada, dejalos ahy, y vamos a darle vida y aplicare un tema que te guste ;)

*Otro aspecto importante: usa una ruta de tu local-disco o en la nube(recomendado), yo uso Mega encryptado y lo alojo ahy, asi nunca perdere mi blog, aunque le tengo un back up hecho en otro sitio tmb :) aprende a hacer back-ups, copias, siempre, es una buena practica.*

Ahora:

```
hugo server #ver tu blog en localhost
hugo server -D  #-D por si hay drafts que lo envie
```

Abre tu navegador: 

```
http://localhost:1313/
```

Y veras una pagina en blanco, ese es nuestro blog, aun falta moldearlo, aunque ponga "not found", no te preoc. por ello ;)

# Tema

Ve a : `https://themes.gohugo.io/` para una gran lista de temas, elije una.

La mayoría de los temas están disponibles en Github y se pueden instalar a través de submódulos. Por ejemplo, para instalar un tema, ve a la carpeta raíz en donde creaste el blog/site `cd ~/myblog` y ejecute lo siguiente:

```
git init  #inicia un .git vacio (un repo) en tu local. Ojo aqui (evite errores): no vuelvas a hacer git init en este proyecto (git estara iniciado para siempre en este proyecto/directorio) palabra de dev;).
git status #hazlo siempre para ver que trabajos hay.
git commit -m "el primer commit" #los commits son como dioses.
git submodule add https://github.com/adityatelange/hugo-PaperMod.git /themes/PaperMod

```

Estamos instalando/aplicando el tema "PaperMod" a nuestro blog como submodulo, en mas adelante lo veras en github tmb.


Ahora:

```
cd ~/myblog #ve a tu blog en hugo.
ls  #ls lista los /dir dentro de tu blog, veras /themes esa carpeta nos interesa.
cd /themes #dentro de /themes.
```

Veras dentro de /themes un dir 'PaperMod' esta descargado y aplicado como submodule en .git, cuando haremos git push (github) se aplicara, pero aun no.

Ahora procedemos a configurar el tema y decirle a hugo que use nuestro tema `PaperMod`. eso lo haremos con un archivo llamado `config.toml`

Importante: que sepas que hugo maneja varios archivos/extensiones/lenguajes como `.yaml` `.yml` `.toml` etc. Si tu config acaba en `.yml` hugo no tendra problema en leerlo, aqui como ves acaba `.toml`. Incluso lo puedes nombrar a `hugo.toml`.

Ve a:
```
cd ~/myblog
code . #abro todo el content de mi blog en vscode (usa el editor que a ti te guste, este paso no es obligatorio)
config.toml #editalo
```

Dentro de config.toml, config.yml, .yaml, etc tienes que anadir:
```
theme = 'PaperMod'  #ojo con usar comillas dobles, o simples.
```

Y listo con esto ya podemos ver nuestro blog en vivo:
```
hugo server #ve a http://localhost:1313/ y veras tu blog/tema ;)
```

Incluso mas facil podemos hacer un: `echo "theme = 'PaperMod'" >> config.toml` y listo. #debes estar en el dir /themes (por si falla).

La estructura basica para empezar de un `hugo.toml` `config.toml` es esta:
```
baseURL = 'https://example.org/' #tu dominio, no olvides asignarlo cuando lo subas a github pages o etc.
languageCode = 'en-us' #importante tenerlo
title = 'My New Hugo Site/Blog' #titulo de tu blog/site
theme = 'PaperMod' #obligatorio
```
Cada tema tiene su modus:Operandi, aunque 95% de ellas se aplican con tan solo `git submodule` pero hay algunas que tienes que copiar cosas/archivos a tu dir /root (tu dir /root en hugo es la carpeta/directorio de tu blog /myblog) te recomiendo que mires bien el github/gitlab de cada tema y leer sus wikis o readme.md.

# Publish the site

[Si vamos al Sitio official de Hugo que es este mismo](https://gohugo.io/getting-started/quick-start/)

Te recomiendo que le eches un vistazo, y que aprendas como publicar articulos/posts (en hugo se llaman /post o /posts), editarlos, crear mas paginas de las que viene por defecto, y un monton de cosas, hugo las tiene bien documentadas y escritas, eso me gusta.

En este /post nos centramos mas en hacer el blog, el deploy y su seguridad mas que nada, ya que con cloudflare lo tendras asegurada.

# IMPORTANTE: 

#### Tanto ahora como en un futuro nunca hagas `hugo` de sitio/blog,  hugo creara tu sitio estatico, hara el build de tu blog/sitio en un dir llamado /public, esa carpeta/directorio es tu blog publico sin deployment(o server), que la tienes que alojar en un servidor/servicio como netlify, heroku, back4app, etc. Pero no es nustero caso, mi metodologia es otra, ya veras.
### Este paso arriba descrito es importantisimo a dia de hoy, porque github pages ya viene incluido y github hara solito el deploy de tu blog hugo, lo vamos a configurar en el repo por defecto, y listo.


# Breve despliegue y profundismo de un blog en hugo (recomiendo leerlo):

`cd ~/myblog  #no olvides /myblog es tu directorio /root`

`ls -l #listar carpetas y directorios en list/ bonito al ojo humano`

* `/archetypes`
**En el contexto de Hugo, un generador de sitios web estáticos, la función /archetypes se utiliza para crear plantillas predefinidas para nuevos contenidos que vayas a agregar a tu sitio. Cuando creas un nuevo contenido, Hugo utiliza estos archivos de arquetipos para generar la estructura inicial del contenido.**
**Los archivos de arquetipos contienen información o campos predefinidos que quieres incluir en ciertos tipos de contenido. Por ejemplo, si estás creando un blog y quieres que cada entrada tenga campos como título, fecha, autor, categoría, etc., puedes definir estos campos en un archivo de arquetipo. Cuando creas una nueva entrada en tu blog, Hugo usará esta plantilla para generar automáticamente la estructura inicial del contenido con los campos que has definido.**
**La función /archetypes en Hugo te permite definir estas plantillas preestablecidas para diferentes tipos de contenido, facilitando la creación de nuevo contenido con una estructura coherente y consistente en tu sitio web.**

* `/content`
**La carpeta /content es una parte fundamental en los sitios web generados por Hugo. En ella se almacenan todos los archivos de contenido, como las entradas del blog, páginas estáticas, documentos, imágenes y cualquier otro tipo de información que desees mostrar en tu sitio.**
**Dentro de la carpeta /content, puedes organizar tu contenido en subcarpetas para una mejor estructura. Por ejemplo, podrías tener una carpeta llamada /blog para las entradas del blog, otra carpeta llamada /about para la página "Acerca de", y así sucesivamente.**
**Cada tipo de contenido suele tener su propia carpeta y archivos asociados. Por ejemplo, una entrada de blog podría tener un archivo Markdown con información sobre esa entrada, como título, fecha, cuerpo del texto, etc.**
**Hugo utiliza la estructura y el contenido de esta carpeta para generar el sitio web estático final. Al ejecutar Hugo, procesa estos archivos de contenido junto con las plantillas y los archivos de configuración para crear páginas web estáticas listas para ser desplegadas en un servidor web o plataforma de alojamiento.**

* `/data`
**La carpeta /data en Hugo es un directorio especial utilizado para almacenar datos estructurados que se pueden acceder en las plantillas del sitio. Contiene información que no está destinada a ser páginas web individuales, pero que puede ser utilizada en múltiples secciones del sitio.**
**Dentro de /data, puedes organizar archivos en diferentes formatos, como JSON, YAML, TOML o CSV, para representar conjuntos de datos estructurados. Estos archivos pueden contener información como configuraciones, listas, diccionarios u otros datos que necesites para tu sitio.**
**Por ejemplo, podrías tener un archivo JSON en /data que almacena información sobre miembros del equipo, un archivo YAML con configuraciones de idiomas o incluso un archivo CSV con datos que quieras mostrar en tablas o gráficos en tu sitio.**
**La carpeta /data ofrece una forma conveniente de separar los datos del contenido de las páginas, lo que hace que sea más fácil mantener y actualizar información que se utiliza en múltiples partes del sitio sin tener que repetirla en diferentes archivos de contenido.**

* `/layouts`
**La carpeta /layouts es un componente clave en Hugo, ya que contiene las plantillas que determinan la estructura y la presentación visual de tu sitio web. En este directorio, se encuentran los archivos de plantillas que Hugo utiliza para renderizar y generar las páginas web a partir del contenido y los datos.**
**Estas plantillas se escriben en lenguajes como HTML con la adición de código en Go, ya que Hugo está basado en Go. Dentro de /layouts, puedes tener subdirectorios que representan diferentes secciones o tipos de páginas en tu sitio, como /_default para las plantillas predeterminadas que se aplican a varios tipos de contenido si no se encuentra una plantilla más específica, o directorios específicos como /blog para plantillas relacionadas con las entradas del blog, /partials para fragmentos de código reutilizables, entre otros.**
**La estructura de /layouts es esencial para definir la apariencia y la estructura general de tu sitio web. Al personalizar o crear nuevas plantillas en este directorio, puedes controlar completamente cómo se presenta tu contenido en las páginas web generadas por Hugo.**

* `/resources`
**En Hugo, la carpeta /resources es un directorio especial utilizado para almacenar y gestionar los activos del sitio web, como imágenes, archivos CSS, JavaScript, archivos de descarga u otros recursos estáticos.**
**Dentro de /resources, puedes organizar estos archivos de manera estructurada, por ejemplo, teniendo subdirectorios como /images, /css, /js, etc., para separar diferentes tipos de recursos. Estos archivos pueden ser referenciados desde tus plantillas para ser incluidos en las páginas generadas por Hugo.**
**La carpeta /resources se utiliza en conjunción con las plantillas para cargar, procesar y gestionar estos activos, permitiendo su inclusión y manipulación en el sitio web final. Además, Hugo proporciona funcionalidades y métodos para trabajar con estos recursos, como transformaciones de imágenes, procesamiento de CSS y JavaScript, entre otros, permitiendo optimizar y personalizar la manera en que se sirven estos activos estáticos en el sitio web.**

* `/static`
**La carpeta /static en Hugo es un lugar especial! Es donde puedes almacenar archivos estáticos que no necesitan ser procesados por Hugo pero se utilizan directamente en tu sitio web. Estos archivos estáticos pueden ser imágenes, archivos CSS, JavaScript, fuentes tipográficas, archivos PDF, y cualquier otro recurso que desees incluir sin modificaciones específicas por parte de Hugo.**
**Cuando colocas archivos en la carpeta /static, Hugo los copia automáticamente en el directorio raíz del sitio web generado cuando construyes tu sitio. Por lo tanto, si tienes una imagen llamada logo.png dentro de /static/images, esta imagen estará disponible en el sitio web como tusitioweb.com/images/logo.png.**
**Esta carpeta es útil para elementos que quieres que se mantengan sin cambios y se sirvan directamente al navegador, sin necesidad de que Hugo realice ninguna manipulación o procesamiento adicional sobre ellos. Es una forma conveniente de incorporar recursos estáticos en tu sitio web de Hugo.**

* `/themes`
**La carpeta /themes en Hugo es un directorio especial donde puedes almacenar y organizar temas para tu sitio web. Los temas son conjuntos de archivos de plantillas, hojas de estilo (CSS), JavaScript y otros recursos que definen la apariencia y el diseño de tu sitio.**
**Dentro de /themes, puedes tener diferentes carpetas, cada una representando un tema específico. Estos temas pueden ser personalizados y configurados para adaptarse a tus necesidades. Al usar temas en Hugo, puedes cambiar fácilmente la apariencia visual y la estructura de tu sitio web sin tener que reescribir todo el código desde cero.**
**Cuando creas un sitio con Hugo, generalmente comienzas con un tema predeterminado, pero la carpeta /themes te permite agregar y cambiar fácilmente entre diferentes temas según tus preferencias. Puedes descargar temas de la comunidad de Hugo o crear tus propios temas personalizados para adaptarse perfectamente a tu sitio.**


* `.gitmodules`
**Los archivos .gitmodules y el uso de submódulos en Git permiten incluir repositorios de Git anidados dentro de un repositorio principal. Esto es útil cuando quieres incluir, por ejemplo, un proyecto externo dentro de tu propio proyecto y mantener un control más granular sobre las versiones y cambios de ese proyecto externo.**
**El archivo .gitmodules es un archivo de configuración de Git que se utiliza para definir los submódulos. Contiene información sobre los submódulos, como la URL del repositorio remoto, la ruta local donde se encuentra el submódulo dentro de tu proyecto, etc.**
**Cuando clonas un repositorio que contiene submódulos y ejecutas git submodule init y git submodule update, Git se encarga de descargar los contenidos de los submódulos y los coloca en los directorios correspondientes según lo especificado en .gitmodules.**
**El uso de submódulos en Git puede ser útil para vincular proyectos relacionados, utilizar bibliotecas externas o mantener un control más estricto sobre dependencias externas en un proyecto más grande. Sin embargo, también puede añadir complejidad a la gestión del proyecto, especialmente al trabajar con equipos o cuando se necesitan actualizaciones frecuentes en los submódulos.**

* `/.config.toml`
**El archivo config.toml es un archivo de configuración fundamental en Hugo, el generador de sitios estáticos. Este archivo, escrito en formato TOML (Tom's Obvious, Minimal Language), contiene configuraciones clave para tu sitio web.**

### En config.toml, puedes definir una variedad de ajustes y parámetros que afectan cómo se construye y se ve tu sitio web. Algunos ejemplos comunes de configuraciones que puedes encontrar en este archivo son:

1.Parámetros generales del sitio: Puedes definir el nombre del sitio, la descripción, la URL base, el idioma predeterminado, entre otros.

2.Configuración del tema: Si estás utilizando un tema en tu sitio de Hugo, puedes configurar opciones específicas del tema en este archivo.

3.Menús de navegación: Puedes definir los elementos del menú de navegación, como enlaces a diferentes secciones del sitio.

4.Configuraciones de SEO: Configuraciones relacionadas con metaetiquetas, descripciones y otros elementos importantes para el SEO.

5.Parámetros de renderizado: Puedes especificar formatos de fecha, lista de formatos admitidos para el procesamiento de contenido, entre otros.

#### El archivo config.toml es esencial para personalizar y configurar cómo se genera tu sitio web con Hugo. Sus ajustes son aplicados durante la construcción del sitio y tienen un impacto directo en cómo se presentan los contenidos y cómo funciona tu sitio en general.


# Deploy Proceed ON IT:

Procederemos a subirlo a github (github-pages):

```
cd ~/myblog #tu /root blog/site.

ls #lista.

git status #buena practica, mira bien el log antes de push--ear y add. No olvides de git init, ya lo hemos hecho.

git add . #git add y punto . al final anade todo los archivos asi como folders en una lista/.espera para subirlos.

git commit -m "second commit ready to upload my blog" #el commit es dios.git, es funda=mental.

git branch -M main #creamos la rama main, trabajaremos en main con git push y deploy;s, no en rama 'master' eso nunca, las buenas practicas ante/todo ;) somos Dev- o no ;)

clear #limpia tu consola/terminal.

git status #ya se soy pesado;)

```

#### Vamos a github a crear el Repo, veee......;): presta ATENCION aqui, tu repositorio se dede llamar nombre de usuario de github, acorde a ello, mas .github.io: `tmcyb3r.github.io`

*Evita que tu blog termine en .github.io/Blog ;)*

Importante en cada repo que creas (palabra de dev.otra vez:::)) en github crea el repositorio limpio sin nada, ni siquiera un readme.md, o gitignore, o licencias, dejalo limpio, y siempre PUSH' todo desde local, aunque lo queres crear, creal;o en local y push it, eso te puede dar problemas, con cargas del repo, y work's in progress, por lo menos asi lo interpreta git siendo muy listo, que lo es.


Tienes el repo creado, hurray:), fijate siempre en que github es tan listo y te ofrece los comandos y la ayuda, pero no vamos a utilizar todo ello, si no que hemos hecho medio-trabajito :)

Proceed:
```
git status #pesaadoo, lo se , hazlo ;)
git add origin remote  #copias y pegas la direccion de tu repo https:// ..............git, y listo, enter.
git push -u origin main #listo hemos empujado todo nuestro blog/site a github, a prtir de ahora solo 'git push'.

Diccionario:
#origin(el origen,e el repo, donde? en main, eso si) 
#main (la rama main) (usala siempre, o nombrala a develop o work, no hay inconveniente, usa un nombre professional;))
```

Ve a : la pestaña /Actions de tu /repo y veras el deploy en vivo ;) asi como algun error que puede succeder, no descarto, es la vida de /devs :)

*Actualiza la pagina de tu repo y veras el contenido subido.*

Ahora necesitamos un dir llamado /workflow/github/gh-pages.yml para la rama gh-pages, a dia de hoy es obsoleto `ojo con esto`, no es necesario, ya que github la tiene como incluida:(Esto si no tienes pensado en alojar tu blog/sitio en github, pero si es otro cliente/servicio entonces posibile que necesites otro tipo de setting).

#### Ve a setting tu repo: 

Arriba del todo veras algo asi:
```
Your site is live at https://tmcyb3r.com/ (en tu caso usuario.github.io)
Last deployed by @tmcybers tmcybers 9 hours ago
```

*Todo correcto.*

#### Ve a:

* 1.Settings
* 2.Pages
* 3.Github Actions (despliega)
* 4.Github Actions de nuevo y elije `Hugo` te aparecera en grande:) pincha en complete y commit de ello en tu repo, y listo, github se encargara del build-ing y deploy de tu blog/site, no tienes que hacer nada mas, eso viene por defecto en github asociado a github-pages para hugo.

El custom domain, si lo tienes de otro provedor que no sea cloudflare, tienes que asignarlo con DNS check (DNS Check in Progress y etc), esto segun cada cliente, con cloudflare lo hacemos en la pagina de ellos, y no en github.

#### Atento: no olvides ahora editar `hugo.toml` o como se llame el tuyo y asignar `baseURL = 'user.github.io'` , o si tienes dominio personal asignalo ahora o antes del deployment.

Ahora de nuevo:

```
cd ~/myblog #/root blog.
ls #list
git status #ya sabes, pesoo pesado;)
git add . #añade todo.
git commit -m "baseURL anadido" #comenta tus jobs siempre.
git push #push-it.

#Listo, ve a /Actions /Deploy y veras tu build-it.
```

### Importante: en `Branches`, despliegue de ello, y ponlo en `main` que es en donde trabajaras siempre, master no se toca, es dios;)

# Cloudflare Deploy

En este paso tienes la cuenta de cloudflare, si no tienes una create-la, es free, no worry (tuve que usar una vpn para ello, de alguna manera cloudflare no le tenia carino a mi ip :) asi que usa una vpn para ello y listo, luego te dejara pasar con tu ip)

##### En 2024, Ve a:

* 1.Workers & Pages
* 2.Overview.
* 3.Pages(arriba derecha)

![Cloudflare](/images_post/cloudflare1.webp)


No subimos nada,solo conectamos el github/gitlab nuestro con cloudflare y lo alojamos en cloudflare para una mayor seguridad y en contra del spam y muchisimo mas (recomiendo cloudflare a todo paso, aunque aveces odiamos los captchas en javascript de ellos:), solo conectas next, next:

Pon un nombre descriptivo hugo-sample es solo de ejemplo;), usa tu nombre de usuario, o nombre personalizado que le pusiste a tu dominio:

![Cloudflare](/images_post/cloudflare2.webp)

# IMPORTANTE: Paso! 

Aqui tendras que rellenar unos datos sobre tu deploy:


| Option | Value | Description
---
| Production branch |	main | This define the branch to use as its source code for production
---
| Framework preset | Hugo | Select Hugo from dropdown list
---
| Build command | hugo | --baseURL $CF_PAGES_URL	| This is the command to build your website
---
| Build output directory | public | By default Hugo output your website to this folder
-----
|Root directory (advanced) | no pongas nada, dejalo vacio |  Use this if your build command should be run in other directory. Leave this empty.
-----
|Environment variables (advanced) | no pongas nada, dejalo vacio | This is useful if you want to pass env vars to your build script. We will use this to control the Node.js & Hugo version
---

#### Save and Deploy.

Veras algo parecido a esto :)
```
21:45:31.248	Executing user command: hugo --baseURL $CF_PAGES_URL
21:45:31.324	Start building sites … 
21:45:31.325	hugo v0.94.2-48FB9E4D+extended linux/amd64 BuildDate=2022-03-12T10:28:42Z VendorInfo=gohugoio
21:45:31.478	
21:45:31.478	                   | EN  
21:45:31.478	-------------------+-----
21:45:31.479	  Pages            |  7  
21:45:31.479	  Paginator pages  |  0  
21:45:31.479	  Non-page files   |  0  
21:45:31.479	  Static files     |  1  
21:45:31.479	  Processed images |  0  
21:45:31.479	  Aliases          |  0  
21:45:31.479	  Sitemaps         |  1  
21:45:31.481	  Cleaned          |  0  
21:45:31.481	
21:45:31.481	Total in 193 ms
21:45:31.488	Finished
21:45:31.489	Note: No functions dir at /functions found. Skipping.
21:45:31.489	Validating asset output directory
21:45:32.340	Deploying your site to Cloudflare's global network...
21:45:38.331	Success: Assets published!
21:45:38.784	Success: Your site was deployed!
```

Ahora haz click : en Continue to project.

Cloudflare te proporciona un dominio gratuito, como hemos dicho anteriormente: acaba en : .pages.dev (la compra del dominio personal es a tu eleccion)

Para ello deberas ir a la pestaña: Custom Domain y asignar o comprar uno.

## Importante paso de nuevo:

Ve a pestana Settings: Environment variables y edita las variables de tu pagina y agrega la siguiente:

```
HUGO_VERSION v0.121.1  #mira bien a dia de hoy en que version esta hugo, lo actualizan cada mes.
```



# ¡Felicitaciones por llegar hasta aqui ;), hemos alojado con éxito su sitio de forma gratuita! Y hemos aprenido Hugo ! Hurray

Escribiré más sobre consejos y trucos con el alojamiento de su SSG con las páginas de CloudFlare en el futuro, incluido el uso de Wrangler para cargar su sitio web para que tenga más control sobre su tubería CI/CD.

*Antes de despedirme, dejame decirte que en cloudflare puedes agregar reglas de paginas o basadas en firewall:*

### Asi como:

* Redireccionar www a non-www
* Redireccionar todo HTTP a HTTPS

Y muchos mas ;)

tmcyb3r