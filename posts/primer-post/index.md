<!--
.. title: Primer Post
.. slug: primer-post
.. date: 2018-05-06 01:42:46 UTC
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

Backstory: Hace algún tiempo tenía un blog en github, con nula actualización excepto para probar algunas características técnicas.
La motivación para el cambio de jekyll a nikola es conocer nuevas formas de bloggear, los desafíos técnicos asociados y proponerse ser un poco más consistente en escribir artículos.

Asumiento una instalación de conda, los pasos para la instalación son los siguientes:

## Ambiente**
Crear un ambiente de trabajo en conda llamado nikola, instalando pip y webassets

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
```
nikola init --quiet sebastiandres_by_nikola
cd sebastiandres.github.io
nikola build
```

## Configuración
Editar la configuración: 

```
nano conf.py
```

## Crear el primer post
Crear el primer post:
```
nikola new_post -f markdown
```

## Crear los archivos html

```
nikola build
```

## Crear repositorio en github

```

```

## Cerrar
```
source deactivate nikola
```

## Links Inspiradores:

* [https://conda.io/docs/user-guide/tasks/manage-environments.html](): Manejar ambientes en conda (en inglés).
* [https://getnikola.com/getting-started.html](): Guia de inicio de nikola (en inglés).
* [https://daringfireball.net/projects/markdown/syntax](): Explicacion de markdown (en inglés).

