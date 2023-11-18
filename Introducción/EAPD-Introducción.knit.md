---
title: "Estadística y Ciencia de Datos: Conceptos Básicos"
subtitle: "Unidad 1 - Introducción"
author: 
  name: "Enver G. Tarazona Vargas <br> peetaraz@upc.edu.pe"
institute: "Estrategias de Análisis y Preparación de Datos <br> Universidad Peruana de Ciencias Aplicadas"
format:
  #Beamer
  revealjs: 
    theme: default
    preview-links: auto
    #theme: ["pp.scss"]
    #theme: [simple, monash.scss]
    css: [styles.css, custom.css]
    slide-number: true
    #multiplex: true
    chalkboard: 
      buttons: true
    title-slide-attributes:
      data-background-image: figuras/UPC_fondo_3.jpg
      data-background-size: cover 
      data-background-color: "black"
    footer: <https://www.upc.edu.pe/>
    logo: figuras/universidad_logo.png
execute:
  echo: true
bibliography: bibliografia.bib
csl: "apa.csl"
lang: Es-es
citation_package: biblatex
#nocite: '@*'
# nocite: | 
#   @R-bookdown, @xie2015
#editor: visual
---




<!-- # Motivación {background="#43464B" background-image="figuras/fondo1.jpg"} -->

## ¿Qué aprenderás? {background="#43464B"}

::: {.incremental style="font-size : 100%"}
1.  Definir la importancia de los datos en la actualidad.
2.  Qué es Estadística y las principales tendencias de análisis de datos.
3.  Definir que es Ciencia de Datos y Machine Learning.
4.  Entender qué es Big Data y su importancia.
:::

# Estadística {background="#43464B" background-image="figuras/fondo1.jpg"}

## La importancia de los datos

::: {.incremental style="font-size : 95%"}
-   Datos = "Petróleo" de la economía digital.

-   Las aplicaciones móviles/online generan grandes flujos de datos.

-   Los especialistas de diversas áreas buscan aprovechar los datos, por ejemplo, para:

    -   `<svg aria-hidden="true" role="img" viewBox="0 0 512 512" style="height:1.5em;width:1.5em;vertical-align:-0.125em;margin-left:auto;margin-right:auto;font-size:inherit;fill:red;overflow:visible;position:relative;"><path d="M225.8 468.2l-2.5-2.3L48.1 303.2C17.4 274.7 0 234.7 0 192.8v-3.3c0-70.4 50-130.8 119.2-144C158.6 37.9 198.9 47 231 69.6c9 6.4 17.4 13.8 25 22.3c4.2-4.8 8.7-9.2 13.5-13.3c3.7-3.2 7.5-6.2 11.5-9c0 0 0 0 0 0C313.1 47 353.4 37.9 392.8 45.4C462 58.6 512 119.1 512 189.5v3.3c0 41.9-17.4 81.9-48.1 110.4L288.7 465.9l-2.5 2.3c-8.2 7.6-19 11.9-30.2 11.9s-22-4.2-30.2-11.9zM239.1 145c-.4-.3-.7-.7-1-1.1l-17.8-20c0 0-.1-.1-.1-.1c0 0 0 0 0 0c-23.1-25.9-58-37.7-92-31.2C81.6 101.5 48 142.1 48 189.5v3.3c0 28.5 11.9 55.8 32.8 75.2L256 430.7 431.2 268c20.9-19.4 32.8-46.7 32.8-75.2v-3.3c0-47.3-33.6-88-80.1-96.9c-34-6.5-69 5.4-92 31.2c0 0 0 0-.1 .1s0 0-.1 .1l-17.8 20c-.3 .4-.7 .7-1 1.1c-4.5 4.5-10.6 7-16.9 7s-12.4-2.5-16.9-7z"/></svg>`{=html} construir y mantener relaciones con los clientes

    -   `<svg aria-hidden="true" role="img" viewBox="0 0 640 512" style="height:1.5em;width:1.88em;vertical-align:-0.125em;margin-left:auto;margin-right:auto;font-size:inherit;fill:red;overflow:visible;position:relative;"><path d="M80 48a48 48 0 1 1 96 0A48 48 0 1 1 80 48zm64 193.7v65.1l51 51c7.1 7.1 11.8 16.2 13.4 26.1l15.2 90.9c2.9 17.4-8.9 33.9-26.3 36.8s-33.9-8.9-36.8-26.3l-14.3-85.9L66.8 320C54.8 308 48 291.7 48 274.7V186.6c0-32.4 26.2-58.6 58.6-58.6c24.1 0 46.5 12 59.9 32l47.4 71.1 10.1 5V160c0-17.7 14.3-32 32-32H384c17.7 0 32 14.3 32 32v76.2l10.1-5L473.5 160c13.3-20 35.8-32 59.9-32c32.4 0 58.6 26.2 58.6 58.6v88.1c0 17-6.7 33.3-18.7 45.3l-79.4 79.4-14.3 85.9c-2.9 17.4-19.4 29.2-36.8 26.3s-29.2-19.4-26.3-36.8l15.2-90.9c1.6-9.9 6.3-19 13.4-26.1l51-51V241.7l-19 28.5c-4.6 7-11 12.6-18.5 16.3l-59.6 29.8c-2.4 1.3-4.9 2.2-7.6 2.8c-2.6 .6-5.3 .9-7.9 .8H256.7c-2.5 .1-5-.2-7.5-.7c-2.9-.6-5.6-1.6-8.1-3l-59.5-29.8c-7.5-3.7-13.8-9.4-18.5-16.3l-19-28.5zM2.3 468.1L50.1 348.6l49.2 49.2-37.6 94c-6.6 16.4-25.2 24.4-41.6 17.8S-4.3 484.5 2.3 468.1zM512 0a48 48 0 1 1 0 96 48 48 0 1 1 0-96zm77.9 348.6l47.8 119.5c6.6 16.4-1.4 35-17.8 41.6s-35-1.4-41.6-17.8l-37.6-94 49.2-49.2z"/></svg>`{=html} personalizar productos y servicios

    -   `<svg aria-hidden="true" role="img" viewBox="0 0 512 512" style="height:1.5em;width:1.5em;vertical-align:-0.125em;margin-left:auto;margin-right:auto;font-size:inherit;fill:red;overflow:visible;position:relative;"><path d="M464 6.1c9.5-8.5 24-8.1 33 .9l8 8c9 9 9.4 23.5 .9 33l-85.8 95.9c-2.6 2.9-4.1 6.7-4.1 10.7V176c0 8.8-7.2 16-16 16H384.2c-4.6 0-8.9 1.9-11.9 5.3L100.7 500.9C94.3 508 85.3 512 75.8 512c-8.8 0-17.3-3.5-23.5-9.8L9.7 459.7C3.5 453.4 0 445 0 436.2c0-9.5 4-18.5 11.1-24.8l111.6-99.8c3.4-3 5.3-7.4 5.3-11.9V272c0-8.8 7.2-16 16-16h34.6c3.9 0 7.7-1.5 10.7-4.1L464 6.1zM432 288c3.6 0 6.7 2.4 7.7 5.8l14.8 51.7 51.7 14.8c3.4 1 5.8 4.1 5.8 7.7s-2.4 6.7-5.8 7.7l-51.7 14.8-14.8 51.7c-1 3.4-4.1 5.8-7.7 5.8s-6.7-2.4-7.7-5.8l-14.8-51.7-51.7-14.8c-3.4-1-5.8-4.1-5.8-7.7s2.4-6.7 5.8-7.7l51.7-14.8 14.8-51.7c1-3.4 4.1-5.8 7.7-5.8zM87.7 69.8l14.8 51.7 51.7 14.8c3.4 1 5.8 4.1 5.8 7.7s-2.4 6.7-5.8 7.7l-51.7 14.8L87.7 218.2c-1 3.4-4.1 5.8-7.7 5.8s-6.7-2.4-7.7-5.8L57.5 166.5 5.8 151.7c-3.4-1-5.8-4.1-5.8-7.7s2.4-6.7 5.8-7.7l51.7-14.8L72.3 69.8c1-3.4 4.1-5.8 7.7-5.8s6.7 2.4 7.7 5.8zM208 0c3.7 0 6.9 2.5 7.8 6.1l6.8 27.3 27.3 6.8c3.6 .9 6.1 4.1 6.1 7.8s-2.5 6.9-6.1 7.8l-27.3 6.8-6.8 27.3c-.9 3.6-4.1 6.1-7.8 6.1s-6.9-2.5-7.8-6.1l-6.8-27.3-27.3-6.8c-3.6-.9-6.1-4.1-6.1-7.8s2.5-6.9 6.1-7.8l27.3-6.8 6.8-27.3c.9-3.6 4.1-6.1 7.8-6.1z"/></svg>`{=html} automatizar los procesos en tiempo real.
:::

------------------------------------------------------------------------


## Big Bang de la Analítica {.scrollable transition="slide" auto-animate="true"}

::: {style="text-align: center"}
![](figuras\analitica.jpg)
:::

------------------------------------------------------------------------

## Estadística

Es un conjunto de métodos científicos para la recolección, organización, análisis e interpretación de datos con la finalidad de realizar conclusiones y tomar decisiones válidas.

::: {.incremental style="font-size : 95%"}
-   **Estadística Descriptiva**: El objetivo de la estadística descriptiva es resumir las principales características de un conjunto de datos a través de tablas, gráficos y medidas numéricas.

-   **Estadística Inferencial**: Se encarga del análisis de los datos con el propósito de realizar conclusiones válidas acerca de la población de donde originalmente se recolectaron estos datos. La Estadística inferencial está basada en la teoría de probabilidades.
:::

---

## Población

::: { style="font-size : 85%"}
Es un conjunto de elementos sobre los cuales se desea investigar una o más características de estos. El número de elementos que conforman una población será denotado por la letra $N$.

Son ejemplos de población:

- Las bolsas de cemento producidas en un día por una fábrica.

- Los hogares de una región.

- Los alumnos que estudian en la Escuela de Posgrado en la UPC.


Una muestra es, por otro lado, un subconjunto de la población. El número de elementos que conforman una muestra será denotado por la letra n. Se dirá que una muestra es aleatoria si sus elementos han sidoseleccionados mediante un procedimiento probabilístico.
:::

# Estadística y Ciencia de Datos {background="#43464B" background-image="figuras/fondo1.jpg"}

## ¿Qué es Ciencia de Datos?

::: {.incremental style="font-size : 85%"}
-   El proceso de usar datos para entender distintas cosas, para entender el mundo que nos rodea.
-   Usar datos para validar una hipótesis sobre un problema o un modelo
-   El arte de de descubrir *insights* y tendencias que se esconden detrás de los datos.
-   Traducir datos en una historia para generar *insights* y de esta manera tomar decisiones estratégicas para una compañía e institución.
-   Es un campo de estudio relacionado con procesos y sistemas, para extraer datos de varias formas, ya sea una forma estructurada o no.
-   Trabajar con datos para encontrar respuestas a las preguntas que se están explorando.
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_01.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_02.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_03.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_04.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_05.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_06.png)
:::

------------------------------------------------------------------------

## ¿Qué es Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_07.png)
:::

------------------------------------------------------------------------

## ¿Por qué el interés reciente en Ciencia de Datos? {.fullslide}

::: {style="text-align: center"}
![](figuras\DS_08.png)
:::

------------------------------------------------------------------------

## Habilidades para Ciencia de Datos

::: {style="text-align: center"}
![](figuras\DS_09.png)
:::

------------------------------------------------------------------------

## Habilidades para Ciencia de Datos {.fullslide}

![](figuras\DS_10.png){fig-align="center"}

------------------------------------------------------------------------

## Habilidades para Ciencia de Datos

::: {style="text-align: center"}
![](figuras\DS_11.png)
:::

------------------------------------------------------------------------

## Habilidades para Ciencia de Datos

## ![](figuras\DS_12.png){fig-align="center"}

## Proyecto de Ciencia de Datos

![](figuras\DS_Steps.png){fig-align="center"}

# Estadística y Machine Learning {background="#43464B" background-image="figuras/fondo1.jpg"}

## Aprendizaje de Máquinas (*Machine Learning*)

![](figuras\ml_persp.png){fig-align="center"}

------------------------------------------------------------------------

## Machine Learning: Contexto Empresarial

Machine Learning ayuda a responder preguntas como:

::: {.incremental style="font-size : 100%"}
-   ¿Qué método de publicidad impulsará más ventas?\
-   ¿Será rentable la remodelación de una tienda costosa?
-   ¿Qué segmento de clientes comprará mi nuevo producto?
-   ¿Cuándo debería reponer el inventario?\
:::

------------------------------------------------------------------------

## Machine Learning: Deportes

## ![](figuras\ml_ejemp1.png){fig-align="center"}

## Machine Learning: Salud

## ![](figuras\ml_ejemp2.png){fig-align="center"}

## Machine Learning: Itinerarios

## ![](figuras\ml_ejemp3.png){fig-align="center"}

## Machine Learning: Planeamiento de Vacaciones

## ![](figuras\ml_ejemp4.png){fig-align="center"}

## Machine Learning vs. Estadística

![](figuras\ml_est.png){fig-align="center"}

------------------------------------------------------------------------

## Machine Learning vs. Inteligencia Artificial

![](figuras\ml_ia.png){fig-align="center"}

------------------------------------------------------------------------

## Data Management System (DMS)

## ![](figuras\DMS.png){fig-align="center"}

## Tipo de Datos en Retail

## ![](figuras\retail_data.png){fig-align="center"}

## Tipo de Datos en Retail

![](figuras\retail_data2.png){fig-align="center" width="10%"}

------------------------------------------------------------------------

## Los 4 fundamentos de ML

![](figuras\ml_fund1.png){fig-align="center"}

------------------------------------------------------------------------

## Los 4 fundamentos de ML

## ![](figuras\ml_fund2.png){fig-align="center"}

## ML: Entendimiento de Datos

![](figuras\ml_entend1.png){fig-align="center"}

------------------------------------------------------------------------

## ML: Entendimiento de Datos

![](figuras\ml_entend2.png){fig-align="center"}

------------------------------------------------------------------------

## ML: Entendimiento de Datos

![](figuras\ml_entend3.png){fig-align="center"}

------------------------------------------------------------------------

### Entendimiento de Datos: Ejemplo en Retail

::: {.incremental style="font-size : 100%"}
-   Agrupar tiendas en conglomerados usando datos del comportamiento del cliente para crear una política operativa única para múltiples tiendas.\
-   Entender datos no estructurados, por ejemplo, textos descriptivos y comentarios.
-   Categorizar a los productos usando datos existentes.
:::

------------------------------------------------------------------------

## ML: Predicción

![](figuras\ml_pred1.png){fig-align="center"}

------------------------------------------------------------------------

## Predicción: Ejemplo en Retail

![](figuras\neural_net.png){fig-align="center"}

------------------------------------------------------------------------

## ML: Toma de Decisiones

![](figuras\ml_des1.png){fig-align="center"}

------------------------------------------------------------------------

## Toma de Decisiones: Ejemplos en Retail

![](figuras\ml_des2.png){fig-align="center"}

------------------------------------------------------------------------

### ML: Inferencia Causal

\

::: {.incremental style="font-size : 100%"}
-   Comprender si una determinada acción, decisión, intervención o cambio de política funcionó o no.

-   Identificar las causas y realizar la atribución (responsable)
:::

------------------------------------------------------------------------

### Inferencia Causal: Ejemplos en Retail

En retail, la inferencia causal nos ayuda a responder preguntas como:

::: {.incremental style="font-size : 100%"}
-   ¿Cuál fue el impacto de las decisiones operativas en el desempeño?

-   ¿Cómo atribuye las estrategias de adquisición de clientes que funcionaron o las que no?
:::

---

## ¿Qué es aprendizaje estadístico?

*Aprendizaje estadístico* es el proceso de aprendizaje a partir de los datos.

::: { style="font-size : 85%"}
Aplicando *métodos estadísticos* a un *conjunto de datos * (llamado el  *conjunto de entrenamiento*), nosotros podemos:

* *extraer conclusiones* acerca de las relaciones entre las variables (**inferencia**) o
* *encontrar una función predictiva*   para nuevas observaciones.  (**predicción**). 

Además, nos gustaría encontrar estructuras en los datos que nos ayuden a aprender algo sobre el mundo real.

<!-- El aprendizaje estadístico juega un rol muy importante en muchas áreas del conocimiento como en ciencias, finanzas y la industria. -->
:::

---

## Aprendizaje Estadístico vs. ML

::: { style="font-size : 85%"}
* El aprendizaje automático surgió como un subcampo de la inteligencia artificial.

* El aprendizaje estadístico surgió como un subcampo de la estadística.

* Hay mucha superposición: ambos campos se centran en problemas supervisados y no supervisados:
     + El aprendizaje automático tiene un mayor énfasis en las _aplicaciones a gran escala y precisión de la predicción_.
     + El aprendizaje estadístico enfatiza los modelos y su _interpretabilidad_, precisión e incertidumbre.

* La distinción se ha vuelto cada vez más borrosa y hay una gran cantidad de superposición de términos y modelos.

* ¡El aprendizaje automático tiene la ventaja en marketing!
:::


# Estadística y Big Data {background="#43464B" background-image="figuras/fondo1.jpg"}

## 

![](figuras\bd_ejemplos.png){fig-align="center" width="120%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata3.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata4.png){fig-align="center" width="110%"}

::: notes
Ejemplo: comparar precios de pasajes de avión
:::

------------------------------------------------------------------------

## 

![](figuras\bigdata5.png){fig-align="center" width="110%"}

::: notes
Ejemplo: conocer posiciones más cercanas de taxis Uber y estimar tiempos de espera
:::

------------------------------------------------------------------------

## 

![](figuras\bigdata6.png){fig-align="center" width="110%"}

::: notes
Ejemplo: reconocer una canción en pocos segundos como Shazam
:::

## 

![](figuras\bigdata7.png){fig-align="center" width="110%"}

::: notes
Ejemplo: combinar distintos sitios de recomendación para un restaurant)
:::

------------------------------------------------------------------------

## 

![](figuras\bigdata8.png){fig-align="center" width="110%"}

::: notes
Ejemplo: reconocer una canción en pocos segundos como Shazam
:::

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica1.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica2.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica3.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica4.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica5.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica6.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica7.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica8.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica9.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica10.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_logica11.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## Las 4 V's del Big Data

## ![](figuras\4-Vs-of-big-data.jpg){fig-align="center"}

## 

![](figuras\bigdata_volumen1.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_volumen2.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_volumen3.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_volumen4.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_volumen5.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

## ![](figuras\bigdata_volumen6.png){fig-align="center" width="110%"}

## 

![](figuras\bigdata_velocidad1.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_velocidad2.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_variedad1.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_variedad2.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

## ![](figuras\bigdata_variedad3.png){fig-align="center" width="110%"}

## 

![](figuras\bigdata_variedad4.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_variedad5.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

## ![](figuras\bigdata_variedad6.png){fig-align="center" width="110%"}

## 

![](figuras\bigdata_variedad7.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_veracidad1.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_veracidad2.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_veracidad3.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## 

![](figuras\bigdata_valor.png){fig-align="center" width="110%"}

------------------------------------------------------------------------

## Big Data: Fuentes

![](figuras\bigdata2.png){fig-align="center"}

------------------------------------------------------------------------

## Big Data: Ejemplo

![](figuras\bigdata1.png){fig-align="center"}

------------------------------------------------------------------------

<!-- ## Referencias -->

<!-- Falta incluir referencias del curso de datos masivos de la UC -->

