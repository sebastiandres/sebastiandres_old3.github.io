<!--
.. title: Prueba de markdown
.. slug: prueba-de-markdown
.. date: 2018-05-08 22:54:44 UTC
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Prueba de Markdown

Este ejemplo ilustra y testea las funcionalidades principales de un archivo markdown, para verificar que el rendering (en pydocs, jupyter notebook, nikola, etc.) funcione correctamente: [código original](/posts/prueba-de-markdown/index.md).

---

## Formato básico

El texto se escribe normalmente, y debería mostrarse sin consideraciones adicionales.

Es posible colocar un nuevo párrafo, con formateo de texto de *italicas* y **negritas**, y casos anidades: **primer *ejemplo* de anidación** y *segundo **ejemplo** de anidación*.

---

## Listas

### Listas enumeradas
Religiones ordenadas por número de seguidores:

1. Islam
2. Católica
3. Hinduismo
4. Budismo

O sea, [la católica es segunda](https://www.guioteca.com/futbol-internacional/los-memes-mas-crueles-contra-la-uc-y-su-nuevo-fracaso-en-el-futbol-chileno/) ;-).

### Listas sin orden
Hay 10 tipos de personas:

* Las que saben binario.
* Las que no saben binario
* Las que no saben contar.

---

## Modificadores de párrafos

### Bloques de código
El código puede escribirse de varias formas:

    # Código de bloque
    Realizado por indentación.
        para cada linea

```
# Código de bloque
Realizado por delimitadores
    para cada linea
```

```python
# Código de bloque para python
Realizado por delimitadores.
    para cada linea
```

También podemos ver `código en linea`.

### Citas

> Any sufficiently advanced technology is indistinguishable from magic. (Arthur C. Clark).

---

## Enlaces

A continuación, colocaremos el mismo enlace con distintos formatos:

* Versión simple, sólo dirección: <https://sebastiandres.github.io/>.
* Versión con texto: [Link](https://sebastiandres.github.io/)
* Versión con definición de link al final del documento: [Link][1].

## Images

Podemos insertar imágenes en variados formatos (gif, jpg, png, svg):

![Alt text](/posts/prueba-de-markdown/colores.gif "Archivo gif") ![Alt text](/posts/prueba-de-markdown/colores.jpg "Archivo jpg") ![Alt text](/posts/prueba-de-markdown/colores.png "Archivo png") ![Alt text](/posts/prueba-de-markdown/colores.svg "Archivo svg")

y sin olvidar un gif animado ![Alt text](/posts/prueba-de-markdown/pbjt.gif "Archivo gif animado").

## Referencias

* <https://www.markitdown.net/markdown>: Ejemplo de Markdown usado como base para este archivo. 

---

  [1]: https://sebastiandres.github.io/
