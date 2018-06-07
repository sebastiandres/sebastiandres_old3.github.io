<!--
.. title: Cálculos Computacionales en Ingeniería - parte 1
.. slug: calculos-computacionales-en-ingenieria-parte-1
.. date: 2018-06-07 03:21:38 UTC
.. tags: 
.. category: 
.. link: 
.. description: Leeme y primera lección
.. type: text
-->

Existe material valioso de python en inglés pero me parece que muchos estudiantes no acceden al contenido precisamente por estar en inglés en lugar de español. Lo cual es perfectamente comprensible, ya es suficientemente difícil aprender algo nuevo, para qué agregarle un idioma adicional. Pensando en ello, me ofrecí a traducir los notebooks de "Engineering Computations" de [Lorena Barba](https://twitter.com/lorenaabarba?lang=es), que ya poseen en inglés lo módulos [1](https://github.com/engineersCode/EngComp1_offtheground), [2](https://github.com/engineersCode/EngComp2_takeoff) y [3](https://github.com/engineersCode/EngComp3_flyatchange).

El modus operandi es el siguiente: traduzco los módulos con ayuda de un script en python que hacen uso de glob y google translate, y luego edito a mano lo que haga falta. El problema es que la corrección a mano requiere más tiempo de lo que pensaba, al menos para un neurótico detallista como yo.
En esta primera traducción lista, existen:

* Archivo [LEEME](https://github.com/engineersCode/EngComp1_offtheground/blob/translation_es/LEEME.md), traducción del [README](https://github.com/engineersCode/EngComp1_offtheground/blob/master/README.md).
* Notebook [traducido al español](https://github.com/engineersCode/EngComp1_offtheground/blob/translation_es/notebooks_es/1_Interactuando_con_Python.ipynb), y versión [original en inglés](https://github.com/engineersCode/EngComp1_offtheground/blob/master/notebooks_en/1_Interacting_with_Python.ipynb).

Notas de la traducción:

* **¿Cómo traducir el "Engineering Computations"?** Creo que una buena traducción (aunque no compacta) es "Cálculos computacionales en Ingeniería". Sólo "cálculos" no le hace justicia a los notebooks, y "cómputos" no me suena bien.

* **¿Qué traducir y que no traducir?** Traduciré los nombres de los notebooks, el archivo README se llamará LEEME, los comentarios, mensajes y valores de strings, de ser necesario. Los nombres de las variables, a menos que sea extremadamente necesario, no los traduciré para garantizar compatibilidad con el notebook original y porque en general en python se programa con variables en inglés para que se lea más facil.

* **¿Traducir keywords, como lists, arrays, etc.?** Me parece que no, porque de todas formas hay que buscar documentación y el código se hace más facil de entender si sabes ese poco de inglés.

* **Respecto a consideraciones de commits**: commit sin output de celdas para mantener los diffs más concisos, pero con output de celdas en la versión final.

* **Los notebooks en español tendrán badges**. Me gustan los badges y permite fácilmente volver al idioma original.
