# 🎬 Laboratorio Pandas: EDA y Unión de Datos

![Netflix Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Netflix_2015_logo.svg/1198px-Netflix_2015_logo.svg.png)

## 📖 Descripción

Este laboratorio tiene como objetivo realizar un análisis exploratorio de datos (EDA) sobre dos conjuntos de datos relacionados con las producciones de Netflix. Se utilizarán técnicas de manipulación de datos con **Pandas** para responder a preguntas clave y realizar la unión de datos entre los siguientes conjuntos de datos:

- **`netflix_originals.csv`**: Información sobre producciones originales de Netflix.
- **`netflix_titles.csv`**: Información general de títulos en la plataforma Netflix.

El propósito es extraer información valiosa sobre la duración, calificaciones y géneros de las producciones, además de comparar títulos originales frente a otros contenidos.

## 🗂️ Estructura del Proyecto

```
├── data/                                         # Contiene los conjuntos de datos originales
│   ├── netflix_originals.csv
│   └── netflix_titles.csv
├── laboratorio-modulo2-leccion02-eda-union/      # Resultados finales, desarrollo de proceso
└── README.md                                     # Descripción del proyecto
```

## 🛠️ Instalación y Requisitos

Este proyecto requiere **Python 3.8+** y las siguientes bibliotecas:

- pandas
- numpy

Para instalar los requisitos, puedes usar el siguiente comando:

```bash
pip install -r requirements.txt
```

## 🚀 Instrucciones de Uso

1. Descarga o clona el repositorio.
2. Coloca los archivos de datos en la carpeta `data/`.
3. Ejecuta los notebooks en la carpeta `notebooks/` para realizar el análisis.

## 📊 Resultados y Conclusiones

### 1. Carga de Datos

El primer paso consiste en cargar el conjunto de datos. Dependiendo del formato de los datos (CSV, SQL, etc.), se debe utilizar una herramienta o biblioteca adecuada para importarlos. En este caso, los datos están en formato CSV, con lo que se puede utilizar `pandas` para cargarlos en un dataframe y poder trabajar con ellos con esta libreria.

Como definicion de los valores de los csv inicial:

**`netflix_originals.csv`**: Contiene información sobre producciones originales de Netflix. Las columnas que nos encontraremos en este conjunto de datos son: 

   - `Title`: Contiene el nombre del título de la producción original de Netflix.

   - `Genre`: Especifica el género o combinación de géneros de la producción.

   - `Premiere`: Indica la fecha de estreno de la producción en Netflix.

   - `Runtime`: Contiene la duración de la producción en minutos.

   - `IMDB Score`: Representa la calificación promedio que la producción ha recibido en la plataforma IMDB.

   - `Language`: Especifica el idioma principal o los idiomas en los que se presenta la producción.

**`netflix_titles.csv`**: Contiene información sobre una variedad de títulos disponibles en la plataforma Netflix, incluyendo tanto películas como series de televisión. Las columnas que nos encontraremos en este conjunto de datos son:

   - `show_id`: Identificador único para cada título en el dataset.

   - `type`: Especifica el tipo de contenido, ya sea "Movie" (película) o "TV Show" (serie de televisión).

   - `title`: Contiene el nombre del título de la producción.

   - `director`: Muestra el nombre del director del título. Puede estar vacío en algunos casos.

   - `cast`: Lista de actores y actrices que participaron en el título. También puede estar vacío en algunos casos.

   - `country`: País o países donde se produjo el título. Esta columna también puede tener valores faltantes.

   - `date_added`: Fecha en la que el título fue añadido al catálogo de Netflix.

   - `release_year`: Año en que el título fue lanzado o producido.

   - `rating`: Clasificación del contenido en términos de audiencia (por ejemplo, PG-13, TV-MA).

   - `duration`: Duración del título. Para películas, se expresa en minutos (e.g., "90 min") y para series en temporadas (e.g., "2 Seasons").

   - `listed_in`: Categorías o géneros bajo los cuales el título está clasificado (por ejemplo, "Documentaries", "TV Dramas").

   - `description`: Breve sinopsis o descripción del contenido del título.

### 2. Revisión Inicial

En esta primera inspeccion tras cargar los datos podemos observar los tamaños ambos:<br>

Por un lado, el tamaño del Dataframe `netflix_original` es de 513 filas y 6 columnas.<br>

Por otro lado, el tamaño del Dataframe `netflix_titles` es de 8807 filas y 11 columnas.<br>

En cuanto a los tipos de datos que estan presentes en cada columna no encontramos con:<br>
En `netflix_original`:<br>
Title    -->      object<br>
Genre     -->     object<br>
Premiere   -->    object<br>
Runtime    -->     int64<br>
IMDB Score -->   float64<br>
Language  -->     object<br>
<br>
En `netflix_titles`:<br>
type      -->      object<br>
title      -->     object<br>
director  -->      object<br>
cast        -->    object<br>
country        --> object<br>
date_added     --> object<br>
release_year -->    int64<br>
rating       -->   object<br>
duration   -->     object<br>
listed_in     -->  object<br>
description   -->  object<br>

En esta primera revisión inicial se ha apreciado que ambos Dataframes comparten titulos en comun y que puede ser interesante realizar una union de ambos archivos para trabajar sobre un unico Dataframe.

### 3. Análisis de Valores Faltantes

En cuanto a los valores nulos observamos que:<br>
- El primero de los archivos scv `netflix_original` esta bastante completo, no se encuentran variables con contenidos nulos lo que indica una buena recogida de datos.<br>
- Por otro lado, el csv `netflix_titles` si que contiene bastantes valores nulos, principalmente en las variables director, cast, country y duration, lo que indica que se deberia de realizar una mayor recogida de datos en esas variables.<br>

Al juntar ambos archivos se genero una nueva tabla con valores nulos o vacios por la falta de recoger datos del resto de peliculas de Netflix.

### 4. Resumen de principales Insights

Al final del análisis exploratorio, se pueden destacar los principales hallazgos obtenidos:<br>
 - Contamos con tablas de diferente tamaño y con tan solo 1 relación (title), lo que provoca muchos valores nulos cuando se unen ambas tablas.<br>
 - En cuanto a las variables, en el primer Dataframe `netflix_original`, no encontramos con que todos los titulos son unicos, el genero mas repetido ha sido Documentary con 132 valores, la Premier mas repetida el 18 de Octubre de 2019 con 5 valores y el Lenguage mas repetido es English con 352 valores, el IMDB Score ha tenido una media de 6,21 y una desviacion tipica de 0,97.<br>
  - En cuanto a las variables, en el segundo Dataframe `netflix_titles`, no encontramos con que todos los titulos tambien son unicos, el type mas frecuente es Movie con 6131 valores, el director con mas peliculas es Rajiv Chilaka	con 19 valores, el cast mas frecuente David Attenborough	con 19 valores, el country mas frecuente es United States	con 2818 y el listed_in mas frecuente Dramas, International Movies	con 362 valores.

## 🔄 Próximos Pasos

- Mejorar la recopilacion de datos en el csv de `netflix_titles`.
- Implementar técnicas avanzadas de visualización para descubrir patrones adicionales en los datos.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar el proyecto, por favor abre un pull request o una issue.

## ✒️ Autores

[Alex](https://github.com/SrAlcast)

---
