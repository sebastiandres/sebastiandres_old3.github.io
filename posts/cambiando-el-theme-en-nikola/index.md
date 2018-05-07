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
        ('/index.html', 'Principal', 'icon-home'),
        ('/archive.html', 'Archivos', 'icon-folder-open-alt'),
        ('/categories/index.html', 'Etiquetas', 'icon-tags'),
        ('/rss.xml', 'RSS', 'icon-rss'),
        ('https://cl.linkedin.com/in/sebastiandres', 'LinkedIn', 'icon-user'),
        ('https://twitter.com/sebastiandres', 'Twitter', 'icon-twitter'),
        ('https://github.com/sebastiandres', 'Github', 'icon-github'),
   )
}
```

Con estos cambios, el blog ahora debería verse así:

![Screenshot](https://sebastiandres.github.io/posts/cambiando-el-theme-en-nikola/ZenTheme.png)


