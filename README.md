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



## 🔄 Próximos Pasos

### 1. Carga de Datos

El primer paso consiste en cargar el conjunto de datos. Dependiendo del formato de los datos (CSV, SQL, etc.), se debe utilizar una herramienta o biblioteca adecuada para importarlos. Por ejemplo, si los datos están en formato CSV, se puede utilizar `pandas` para cargarlos en un dataframe.

### 2. Revisión Inicial

Una vez cargados los datos, es fundamental realizar una inspección básica del conjunto de datos.<br>
- Visualizar las primeras filas para tener una idea del contenido.
- Comprobar las dimensiones del dataset (número de filas y columnas).
- Revisar los tipos de datos presentes en cada columna.
- Detectar la presencia de valores faltantes o duplicados.
En esta primera inspeccion podemos observar los tamaños de los dos archivos csv:<br>
Por un lado, el tamaño del csv netflix_original es de
Por otro lado, el tamaño del csv netflix_titles
### 3. Análisis de Valores Faltantes

En cuanto a los valores nulos observamos que:<br>
El primero de los archivos scv #netflix_original# esta bastante completo, no se encuentran variables con contenidos nulos lo que indica una buena recogida de datos.<br>
Por otro lado, el csv #netflix_titles# si que contiene bastantes valores nulos, principalmente en las variables director, cast, country y duration, lo que indica que se deberia de realizar una mayor recogida de datos en esas variables.<br>

Al juntar ambos archivos se genero una nueva tabla con valores nulos o vacios por la falta de recoger datos del resto de peliculas de Netflix.

### 4. Resumen de principales Insights

Al final del análisis exploratorio, se pueden destacar los principales hallazgos obtenidos:
- Describir los patrones generales observados en los datos.
- Mencionar las relaciones más relevantes entre las variables numéricas o categóricas.
- Explicar cómo se abordaron los valores faltantes o anomalías detectadas.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar el proyecto, por favor abre un pull request o una issue.

## ✒️ Autores

[Alex](https://github.com/SrAlcast)

---
