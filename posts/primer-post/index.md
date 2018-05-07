<!--
.. title: Primer Post
.. slug: primer-post
.. date: 2018-05-06 01:42:46 UTC
.. tags: nikola, blog
.. category: 
.. link: 
.. description: 
.. type: text
-->

*Backstory*: Desde hace algún tiempo tengo un blog en github, abandonado a su suerte y con nula actualización excepto para probar algunas características técnicas. El blog se basa en el template de jekyll más algunos tuneos propios, y resulta interesante porque es el mismo github el que genera el html. 
La motivación para el cambio de jekyll a nikola es conocer nuevas formas de bloggear, los desafíos técnicos asociados y proponerse ser un poco más consistente en escribir artículos, además de tener un control mucho más cercano de la generación del html: ahora puedo visualizar exactamente cómo se verá el post sin necesidad de hacer el commit y el rendering en github.

Asumiendo una instalación previa de conda, los pasos para la instalación son los siguientes:

## Ambiente
Crear un ambiente de trabajo en conda llamado nikola, instalando pip. Instalar la librería nikola, y luego instalar webassets (sino dará error más adelante para compilar el blog).

```
conda create --name nikola pip
conda activate nikola
conda install webassets
```

## Instalar Nikola
Instalamos la última versión de Nikola:

```
pip install -U --upgrade-strategy=eager Nikola==8.0.0b1
```

## Crear el blog
Inicializamos el blog, sin contenido dummy (opción `--quiet`). 

```
nikola init --quiet sebastiandres_by_nikola
cd sebastiandres_by_nikola
```

## Configuración
Editamos la configuración, para colocar algunas cosas básicas como nombre del blog y detalles como ésos. Podremos editarlo más adelante: 

```
nano conf.py
```

## Crear el primer post
Creamos el primer post, en markdown:

```
nikola new_post -f markdown
```

El paso anterior nos pedirá un nombre para el post, y tendremos que editarlo. En mi caso, corresponde a este post que estás leyendo y cuyo contenido en markdown puedes ver [acá](https://sebastiandres.github.io/posts/primer-post/index.md) (o seguir el enlace que dice "Source" al inicio de cada post).


## Crear los archivos html
Nikola funciona creando todos los archivos htmls asociados a los posts que hayas creado. El blog no es el directorio sebastiandres_by_nikola, sino la carpeta **output** que contendrá el html listo para ser navegado (y subido a la web).

```
nikola build
```

## Crear repositorio en github
En https://github.com/new crear un nuevo repositorio, del tipo nombre-usuario.github.io para que sirva como blog. En mi caso, el blog será sebastiandres.github.io
```
cd output/
git init
git add *
git commit -am "Blog con primer post"
git remote add origin git@github.com:sebastiandres/sebastiandres.github.io.git
git push -u origin master
```

## Visitar
Ahora podemos ver cómo quedó todo, visitando el sitio https://nombre-usuario.github.io/ o en mi caso, [https://sebastiandres.github.io/](https://sebastiandres.github.io/). Deberia verse algo así:

![Screenshot](https://sebastiandres.github.io/posts/primer-post/PrimerPost.png)

Listo, no era tan dificil configurar el blog con los valores por defecto.

## Cerrar
Por último, cerramos el ambiente de trabajo que hemos creado.

```
source deactivate nikola
```

## Links útiles:

* [https://conda.io/docs/user-guide/tasks/manage-environments.html](https://conda.io/docs/user-guide/tasks/manage-environments.html): Manejo ambientes en conda (en inglés).
* [https://getnikola.com/getting-started.html](https://getnikola.com/getting-started.html): Guía de instalación inicial de nikola (en inglés).
* [https://daringfireball.net/projects/markdown/syntax](https://daringfireball.net/projects/markdown/syntax): Explicacion de markdown (en inglés).

