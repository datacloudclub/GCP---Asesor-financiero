# GCP: Proyecto de Asesor Financiero

## Objetivo

Generar una propuesta de valor a través de la ingesta de datos históricos y en tiempo real de la valorización bursátil de las 10 empresas más importantes de NASDAQ-100.

Para ello se implementará una infraestructura en la nube utilizando:

1. máquina virtual para la ingesta de datos utilizando la biblioteca Yfinance en Python
2. almacenamiento en Cloud Storage para alojar los datos en crudo
3. procesamiento de la información almacenada mediante Cloud Functions para
4. alimentar el data warehouse BigQuery
5. utilizar SQL para hacer consultas a BigQuery
6. visualización de data en Looker y conexión con PowerBI
7. modelos de machine learning a partir de la información recabada

## Tabla de contenidos

* [Objetivo](#objetivo)
* [Introducción](#introducción)
* [Descripción de las tecnologías utilizadas](#Descripción-de-las-tecnologías-utilizadas)
* Prerequisitos

## Introducción

El presente proyecto utiliza una máquina virtual en GCP para crear un ambiente de trabajo en Python y un servidor para generar un entorno de Jupyter. El beneficio de contar con una máquina virtual directamente en la nube, nos permite solucionar varios inconvenientes:

1. Primero que nada, si no disponemos de una buena computadora, difícilmente podamos utilizarla para abrir o producir grandes cantidades de información.
2. Segundo, ya nos encontramos trabajando dentro de la propia plataforma. Conectar con otros servicios se convierte en una tarea mucho más sencilla porque todo el proceso se lleva a cabo en la nube, queriendo decir que a medida que tengamos mayor conocimiento de las herramientas disponibles más fácil será adaptar nuestra infraestructura existente y generar propuestas que agreguen valor.

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

## Prerequisitos
