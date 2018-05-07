<!--
.. title: Cambiando el theme en Nikola
.. slug: cambiando-el-theme-en-nikola
.. date: 2018-05-07 00:50:24 UTC
.. tags: nikola, blog
.. category: 
.. link: 
.. description: 
.. type: text
-->

El theme por defecto de nikola tiene un amplio espacio de mejora. Vamos a cambiarlo por uno más agradable.

## Cambiando el theme

En [https://themes.getnikola.com/](https://themes.getnikola.com/) están los temas actuales, de los cuales el tema Zen es el que más me gusta.
Para instalarlo, usamos el comando

```
nikola theme -i zen
```

Luego, y tal como nos indican tras la instalación, en el archivo conf.py se deben configurar:

```
    THEME="zen"
```

y además

```
    NAVIGATION_LINKS = {
        DEFAULT_LANG: (
            ('/index.html', 'Home', 'icon-home'),
            ('/archive.html', 'Archives', 'icon-folder-open-alt'),
            ('/categories/index.html', 'Tags', 'icon-tags'),
            ('/rss.xml', 'RSS', 'icon-rss'),
            ('https://getnikola.com', 'About me', 'icon-user'),
            ('https://twitter.com/getnikola', 'My Twitter', 'icon-twitter'),
            ('https://github.com/getnikola', 'My Github', 'icon-github'),
        )
    }
```

Opcionalmente, también cambié el color principal de azul (#5670d4) a rojo (#7C0A02).

```
THEME_COLOR = '#7C0A02'
```

