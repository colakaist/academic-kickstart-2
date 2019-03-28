---
title: "Practica 1: Primera estimación regresión simple"
subtitle: "Estadistica Multivariada - Sociología FACSO Universidad de Chile"
author: "Juan Carlos Castillo & Alejandro Plaza"
output:
  html_document:
    theme: flatly
    highlight: tango
    toc: true
    toc_float: true
    toc_depth: 2
    number_sections: true
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```


# Introducción

En esta práctica se abordan ejercicios iniciales de regresión simple. Para ello nos vamos a basar principalmente en el ejemplo de Darlington & Hayes cap. 2 (The simple regression model).

# Datos

Los datos a utilizar corresponden a un ejemplo ficticio de 23 casos (individuos) y sus datos en dos variables relacionadas con un juego (originalmente de mini-golf ... pero pensemos en un ejemplo más cercano de taca-taca). Las dos variables de esta base de datos son el número de veces que se ha jugado antes (X) y el número de goles o puntos ganados (Y). El archivo de datos es taca.txt.

Los datos se pueden bajar en el siguiente [link:](https://juancarloscastillo.github.io/jc-castillo/documents/multiva/sesiones/3regsimp1/practica/golf.txt)

Para abrirlos datos recordemos que en la lógica de R se debe generar un objeto donde se guardan los datos. Este objeto puede tener cualquier nombre, en este caso lo llamaremos simplemente "datos". Recordemos que para crear un objeto en `R` la forma típica es `objeto <-función(argumentos)`. Para abrir la base de datos utilizaremos la función `read.csv`, que es para datos guardados en formato de texto simple, separados por coma, tabulación o espacio). En nuestro caso los datos están separados por espacio, así que agregamos además de la ruta del archivo el argumento `sep=""`

```{r eval=FALSE}
datos<- read.csv("( ...ruta hacia el archivo ...)\golf.txt", sep="")
```

<div class="alert alert-info">
  <strong>Rutas:</strong> ¿Cómo identifico la ruta hacia mi archivo? Dos maneras:

  - 1. Boton derecho sobre el archivo -> propiedades, ahí aparece la ruta completa. Copiar y pegar donde corresponde en el archivo de R, no olvidar agregar al final el nombre completo del archivo.

  - 2. Más fácil: mouse sobre archivo, boton derecho, _copiar_ (o ctrl+c); luego, en el archivo de R, en el lugar que corresponde _pegar_ (o ctrl+v)
</div>

```{r echo=FALSE}
datos<- read.csv("https://juancarloscastillo.github.io/jc-castillo/documents/multiva/sesiones/3regsimp1/practica/golf.txt", sep="")
```

## Verificación y descriptivos

Verificamos si los datos están siendo bien leidos:
```{r eval=FALSE}
View(datos)
```
