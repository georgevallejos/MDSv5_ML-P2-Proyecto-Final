# NLP - Clasificación Automática de Tickets

## Índice

- [Índice](#índice)
- [Introducción](#introducción) 
  - [Métodos Utilizados](#métodos-utilizados)
  - [Tecnologías](#tecnologías)
- [Descarga y Configuración](#descarga-y-configuración)
  - [Requisitos Previos](#requisitos-previos)
  - [Cómo Ejecutar](#cómo-ejecutar)
- [Declaración del Problema](#declaración-del-problema)
  - [Objetivo General](#objetivo_general)
  - [Objetivos Especificos](#objetivos_especificos)
  - [Preparación de Datos:](#preparación-de-datos)
  - [Conclusiones](#conclusiones)

## Introducción

El presente proyecto contiene información detallada sobre incidentes criminales reportados desde el año 2020 en adelante, proporcionando un registro detallado sobre cada evento. Las características que tiene el conjunto de datos incluyen fechas, horarios, ubicaciones, características de los delitos y datos demográficos de las víctimas. El dataset brinda información para la identificación de patrones delictivos, análisis de incidencia en diferentes áreas y demografías, así como la facilitación de la distribución de políticas y estrategias de seguridad pública basadas en datos. Esta información puede ser usada tanto para propósitos operativos (intervención policial) como estratégicos (prevención y educación).
Tamaño y Escala Temporal del DataSet:
- Rango Temporal: Desde 2020 hasta el presente, lo cual permite un análisis a corto, mediano y largo plazo.
- Escala Geográfica: Los datos del Dataset solo están enfocados a una ciudad de los EE.UU. 

### Métodos Utilizados

Algoritmo de aprendizaje:
	Factorización de matrices no negativas (NMF): Es un algoritmo de aprendizaje automático que se utiliza para descomponer una matriz no negativa.

Modelos de Machine Learning:
	- Regresión Logística
	- Árbol de Decisión
	- Bosque Aleatorio
	- Naive Bayes

### Tecnologías
	- Software: Google Colaboratory
	- Lenguaje de programación: Python
	- Bibliotecas o librerías de análisis y manipulación de datos:
		Pandas
		Seaborn
	- Bibliotecas o librerías:
 		folium
		HeatMap
  		train_test_split
    		RandomForestClassifier
      		LogisticRegression
		KMeans
      		LabelEncoder
		classification_report, confusion_matrix
  		SimpleImputer
    		StandardScaler
      		IsolationForest
		Model  		
    		OneHotEncoder
	- Herramientas de visualización de datos
		Matplotlib
		Seaborn
		plotly

## Descarga y Configuración
### Requisitos Previos

Este proyecto necesita Google Colaboratory para la ejecución.

### Cómo Ejecutar

Puede descargar el código fuente clonando este repositorio usando Git:

1. Abra su aplicación Terminal favorita (Unix, Linux o Macos), como Terminal, Comando, Consola, iTerm2, etc.

2. Clone el repositorio

```
https://github.com/georgevallejos/MDSv5_ML-Proyecto_Final.git
```

3. Abra el archivo notebook **MDSv5_ML-Proyecto-Final_Grupo_5.ipynb** en Google Colaboratory

4. Extraer el Dataset del RAR file y cargarlo al Colab.

5. Ejecute todos los pasos en Google Colaboratory, las librerias requeridas seran importadas por defect

   Note, el colap le pedira reiniciar la sesion para importar las librerias correctamente
   


## Declaración del Problema

La policía y las autoridades locales enfrentan desafíos constantes en su lucha contra la delincuencia, un fenómeno complejo que varía significativamente según las características sociales, económicas y geográficas de cada comunidad. Los incidentes delictivos no solo generan un impacto directo en la calidad de vida de las personas, sino que afectan de manera desproporcionada a ciertos barrios y grupos vulnerables, intensificando la percepción de inseguridad y dificultando la cohesión social.
El proyecto tiene como propósito abordar varios aspectos críticos:
 - Identificación de patrones temporales y geográficos.
 - Clasificación de tipos de crimen y factores asociados.
 - Detección de anomalías en patrones delictivos.
 - Planificación de estrategias de seguridad pública.


### Objetivo General

Desarrollar un modelo predictivo que brindará información de patrones delictivos y otros factores asociados a los crímenes registrados en el dataset (datos históricos). 

Aplicar modelos supervisados de Machine Learning.

### Objetivos Específicos
 - Identificar zonas/áreas de alta incidencia delictiva mediante el análisis geográfico de los datos de ubicación y características de cada incidente.
 - Determinar patrones temporales de los crímenes reportados.
 - Analizar el perfil demográfico de las víctimas con el fin de entender qué grupos poblacionales son más vulnerables a ciertos tipos de crímenes.
 - Desarrollar modelos predictivos utilizando técnicas de machine learning para anticipar la ocurrencia de delitos en ciertas áreas y horas.
 - Generar gráficos (como mapas de calor y gráficos interactivos) que faciliten la interpretación de los datos y apoyen la toma de decisiones.


### Preparación de Datos:

1. Importar el dataset (formato .CSV)
2. Limpieza de Datos y Análisis de Datos Faltantes.
   Inspección del dataframe
   Imprimir las columnas
   Remover registros nulos
4. Procesamiento de texto
   Codigicar Columnas
   Genrar un Dataset limpio 
6. Análisis exploratorio de datos (EDA)
   Análisis de los tipos de datos
   Análisis las caracteristicas mas relevantes
9. Construcción de modelos mediante aprendizaje supervisado
   Modelo de Prediccion de crimeres
   Modelo de detección de anomalías
   Modelo identificación de hotspots de crimen
   Modelo análisis de relaciones entre factores demográficos y criminalidad
   Generar graficos para visualizar los resultados

### Conclusiones
- Se identificaron las zonas/áreas con alta incidencia delictiva mediante el análisis geográfico según los datos de ubicación y características de cada incidente.
  - Cluster 0 (266841): Central, Hollywood, Rampart, Olympic, Northeast, Hollenbeck, Newton, Southwest, Foothill, Wilshire, N Hollywood
  - Cluster 1 (216541): Van Nuys, Mission, West Valley, Topanga, N Hollywood, Foothill, Devonshire, West LA
  - Cluster 2 (149118): Southwest, Southeast, Newton, 77th Street, Pacific, Harbor
  - Cluster 3 (169036): Southwest, Wilshire, West LA, N Hollywood, Pacific, Hollywood, Van Nuys
  - Cluster 4 (33201): Harbor
- Se identificaron patrones temporales de los crímenes reportados.
- Si bien los crímenes ocurren durante todo el año, la incidencia de estos incrementa considerablemente entre los meses de Diciembre a Enero.
- Se analizó el perfil demográfico de las víctimas con el fin de entender qué grupos poblacionales son más vulnerables a ciertos tipos de crímenes.
  - La frecuencia de víctimas se centra en las edades donde este alcanza un 40% según el modelo.
  - El origen étnico o raza de las víctimas es otro factor que resalta más alcanzando el 30%.
  -   - El sexo de las victimas es otro factor obteniendo el 20% de las víctimas.


