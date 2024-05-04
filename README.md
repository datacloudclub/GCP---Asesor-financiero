# GCP: Proyecto de Asesor Financiero

## Objetivo

Generar una propuesta de valor a través de la ingesta de datos históricos y en tiempo real de la valorización bursátil de las 10 empresas más importantes de NASDAQ-100.

Para ello se implementará una infraestructura en la nube utilizando:

1. máquina virtual para la ingesta de datos utilizando la biblioteca Yfinance en Python,
2. almacenamiento en Cloud Storage para alojar los datos en crudo,
3. procesamiento de la información almacenada mediante Cloud Functions para
4. alimentar el data warehouse BigQuery,
5. utilizar SQL para hacer consultas a BigQuery,
6. visualización de data en Looker y conexión con PowerBI,
7. modelos de machine learning a partir de la información recabada, y
8. mantener la base de datos actualizada diariamente.

## Tabla de contenidos

* [Objetivo](#objetivo)
* [Introducción](#introducción)
* [Descripción de las tecnologías utilizadas](#Descripción-de-las-tecnologías-utilizadas)
* [Aclaración sobre posibles gastos](#Aclaración-sobre-posibles-gastos)
* [Requisitos]()
* Paso 1
  * [Creación de cuenta de Gmail y activación de período de prueba](#creación-de-cuenta-de-Gmail-y-activación-de-período-de-prueba)
  * [Compartir el saldo del período de prueba con otras personas](#compartir-el-saldo-del-período-de-prueba-con-otras-personas)

## Introducción

El presente proyecto tiene como objetivo familiarizar con las herramientas elementales de Google Cloud Platform para el desarrollo de una arquitectura de carga y gestión de datos.

Se parte desde una máquina virtual que nos permita conectarnos de manera remota para aprovechar al máximo el período de prueba y entender cómo funciona la computación en la nube.

Además, debido a que el presente proyecto tiene como fuente de ingesta de datos una biblioteca de Python, se cree conveniente y de bajo costo el uso de una máquina virtual para extraer información y hacer webscraping para analizar las empresas con mayor valuación de mercado.

Al mismo tiempo, al generar un despliegue de principio a fin en la nube, nos facilita mucho la interacción entre los distintos servicios dado que todas las instancias de análisis y transformación de la información ocurren dentro de un mismo entorno. 

En este sentido, ofreceremos un producto de Machine Learning aprovechando la máquina virtual y la velocidad de BigQuery para procesar la información de manera que podamos evaluar tendencias del mercado burstil. 

De las estrategias empleadas en el presente proyecto, podemos destacar el potencial de información que se puede extraer para analizar y la funcionalidad en la nube para elaborar un producto que provea de información actualizada diariamente. 

## Descripción de las tecnologías utilizadas

[![VM](https://img.shields.io/badge/VM-Plataforma_de_Google_Cloud-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/compute/) - Máquina virtual para ejecutar aplicaciones.

[![Bucket](https://img.shields.io/badge/Bucket-Almacenamiento_de_Google_Cloud-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/storage/) - Solución de almacenamiento para guardar datos.

[![BigQuery](https://img.shields.io/badge/BigQuery-Google_BigQuery-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/bigquery/) - Almacén de datos completamente gestionado por GCP para posterior análisis.

[![BigQueryML](https://img.shields.io/badge/BigQueryML-Google_BigQuery-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/bigquery-ml/) - Aprendizaje automático en BigQuery para crear y ejecutar modelos de aprendizaje automático en SQL.

[![SQL](https://img.shields.io/badge/SQL-Google_BigQuery-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/bigquery/sql-reference/) - Consultas SQL estándar para interactuar con datos en BigQuery.

[![GCP Functions](https://img.shields.io/badge/GCP_Functions-Funciones_de_Google_Cloud-blue?style=flat-square&logo=google-cloud)](https://cloud.google.com/functions/) - Funciones sin servidor para aplicaciones basadas en eventos.

[![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)](https://www.python.org/) - Lenguaje de programación utilizado.

[![Pandas](https://img.shields.io/badge/Pandas-Biblioteca_de_Python-blue?style=flat-square&logo=pandas)](https://pandas.pydata.org/) - Manipulación y análisis de datos.

[![NumPy](https://img.shields.io/badge/NumPy-Biblioteca_de_Python-blue?style=flat-square&logo=numpy)](https://numpy.org/) - Computación numérica.

[![Matplotlib](https://img.shields.io/badge/Matplotlib-Biblioteca_de_Python-blue?style=flat-square&logo=matplotlib)](https://matplotlib.org/) - Crear visualizaciones estáticas, animadas e interactivas.

[![scikit-learn](https://img.shields.io/badge/scikit_learn-Biblioteca_de_Python-blue?style=flat-square&logo=scikit-learn)](https://scikit-learn.org/) - Aprendizaje automático.

[![TensorFlow](https://img.shields.io/badge/TensorFlow-Biblioteca_de_Python-blue?style=flat-square&logo=tensorflow)](https://www.tensorflow.org/) - Framework de aprendizaje profundo.

[![Keras](https://img.shields.io/badge/Keras-Biblioteca_de_Python-blue?style=flat-square&logo=keras)](https://keras.io/) - API de redes neuronales de alto nivel.

[![NLTK](https://img.shields.io/badge/NLTK-Biblioteca_de_Python-blue?style=flat-square&logo=nltk)](https://www.nltk.org/) - Procesamiento de lenguaje natural.

[![Statsmodels](https://img.shields.io/badge/Statsmodels-Biblioteca_de_Python-blue?style=flat-square&logo=statsmodels)](https://www.statsmodels.org/) - Estimación e interpretación de modelos estadísticos.

[![Pillow](https://img.shields.io/badge/Pillow-Biblioteca_de_Python-blue?style=flat-square&logo=pillow)](https://python-pillow.org/) - Biblioteca de imágenes para Python.



## Aclaración sobre posibles gastos

* Cada cuenta de Gmail, cuenta con un período de prueba de 90 días y un saldo de US$300 para usar en GCP.
* Durante este período, no se genera ningún tipo de cargo.
* El uso por los servicios de GCP generan gastos que son absorbidos por el saldo de US$300.
* De esta manera podemos analizar el consumo eventual que genera operar utilizando GCP.
* Un objetivo de este proyecto es la reducción de costos probando diferentes alternativas.
* Para acceder a este beneficio, es necesario disponer de una tarjeta de crédito o débito habilitada.
* No se genera ningún cargo en la tarjeta, pero durante el período de prueba no se puede eliminar la tarjeta de la cuenta, de lo contrario, no se puede seguir usando el período de prueba.
* La cuenta de GCP se paraliza automáticamente pasados los 90 días o si el saldo llega a US$ 0.
* Es decir, no hay problema si olvidamos servicios encendidos. Todos ellos serán inhabilitados llegado ese punto.
* Todavía podemos acceder a la información relacionada con el proyecto y se conserva todo aquello que está incluido en la capa gratuita de GCP.
* Se pueden asignar todos los proyectos a una otra cuenta de facturación (por ejemplo, una cuenta que disponga saldo del período de prueba) para poder proseguir con el uso de los servicios.

## Requisitos

* Disponer de una cuenta de facturación bajo período de prueba o activada.
* Tarjeta bancaria (crédito o débito)
* Un compañero bondadoso con una cuenta de facturación bajo período de prueba o activada que quiera compartir el saldo.

## Paso 1

### Creación de cuenta de Gmail y activación de período de prueba

* Ver la siguiente guía: [Cómo acceder a la prueba gratituita con un crédito de US$300 para usar GCP](./Guías/como_acceder.md)

### Compartir el saldo del período de prueba con otras personas

* Ver la siguiente guía: [Cómo habilitar a otros compañeros a usar mi cuenta de facturación para que podamos trabajar colaborativamente sin que tengan que activar el período de prueba gratuito]()
