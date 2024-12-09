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
  - [Objetivo Comercial](#objetivo-comercial)
  - [Preparación de Datos:](#preparación-de-datos)
  - [Construcción y Evaluación del Modelo](#construcción-y-evaluación-del-modelo)
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
		NumPy
	- Bibliotecas o librerías de NLP:
		nltk
		nltk.tokenize
		nltk.corpus
		nltk.stem
	- Bibliotecas de código abierto para NLP:
		SpaCy, ofrece una amplia gama de funciones
		PyCaret, simplifica el proceso de creación, evaluación e implementación de los modelos
	- Modelo de lenguaje
		en_core_web_sm, divide el texto en tokens individuales
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

3. Abra el archivo notebook **MDSv5_ML_P2_Clasificacion_ Automatica_ de_ Tickets_Grupo 5.ipynb** en Google Colaboratory

4. Extraer el Dataset del RAR file y cargarlo al Colab.

5. Ejecute todos los pasos en Google Colaboratory, las librerias requeridas seran importadas por defect

   Note, el colap le pedira reiniciar la sesion para importar las librerias correctamente
   


## Declaración del Problema

Los datos del dataset reflejan distintas quejas de los clientes en función de los productos y servicios, lo que implica una revisión individual de las quejas lo que ocasiona que la atención no sea oportuna; por lo tanto, este inconveniente puede subsanarse con la estratificación de las quejas en grupos específicos.

### Objetivo Comercial

Segregar los tickets de quejas en las categorías más relevantes para brindar al cliente una resolución oportuna.

Aplicar modelos supervisados de Machine Learning.

### Preparación de Datos:

1. Importar el dataset (formato .json)
   Los datos están en formato JSON y se convierte a un dataframe.
2. Limpieza de Datos y Análisis de Datos Faltantes.
   Inspección del dataframe
   Imprimir las columnas
   Asignar nuevos nombres de las columnas
   Asignar NAN en lugar de los datos faltantes en la columna de quejas
3. Procesamiento de texto
   Cambiar el texto en minúsculas
   Eliminar el texto entre corchetes
   Depurar la puntuación
   Eliminar las palabras que contienen números 

   Lematizar los textos
   Extraer las etiquetas POS del texto lematizado    
4. Análisis exploratorio de datos (EDA)
   Visualizar los datos en función a la longitud de caracteres
   Tomando una nube de palabras, encuentre las top 40 palabras que se presenten con mayor frecuencia
   Encontrar los mejores unigramas, bigramas y trigramas por frecuencia entre las quejas 
   Aplicar la métrica TF-IDF (medida de la importancia de una palabra en un documento en comparación con un corpus de documentos más grandes)
   Implementar la técnica no supervisada (NMF)
5. Modelado de temas
   Se requiere adoptar el enfoque de prueba y error con el fin de encontrar la mejor cantidad de tópicos para el modelo NMF.
6. Construcción de modelos mediante aprendizaje supervisado
   Esta sección consiste en la clasificación automática de cualquier nueva queja
7. Entrenamiento y evaluación de modelos
8. Inferencia de modelos

### Conclusiones
- Se limpiaron las quejas eliminando caracteres, puntuación y números innecesarios y convirtiendo el texto a minúsculas.
- La lematización y el filtrado de categorías gramaticales enfocaron el texto en sustantivos para retener información significativa.
- Los términos de alta frecuencia como "credit," "card," "account," and "payment"  resaltaron problemas comunes de los clientes.
- Las nubes de palabras y el análisis de n-gramas revelaron patrones de quejas específicos, como: disputes, account issues, and mortgage problems.
- La vectorización TF-IDF capturó los términos en relación con el corpus de quejas, enfatizando las palabras distintivas en cada tema. Esta punto permitió que el modelo diferenciara entre quejas en función de distribuciones de palabras únicas.
- Se aplicó NMF para agrupar las quejas, los temas facilitaron la clasificación y la comprensión de las inquietudes comunes de los clientes y los ajustes manuales garantizaron la precisión y la interpretabilidad.
- PyCaret simplificó la selección y validación del modelo, lo que confirmó que la regresión logística es la mejor opción.
- La Inferencia del modelo demostro que es posible reutilizar el modelo para clasificar nuevas muestras de datos y asignar los números de Topics correctamente a los grupos definidos durante el entrenamiento.

Resultado de PyCaret que demuestra que el mejor modelo es Logistic Regression:

Model |	Accuracy | AUC | Recall	| Precision	| F1	| Kappa	| MCC	| TT (Sec)
--- | --- | --- | --- | --- | --- | --- | --- | --- |
lr	| Logistic Regression	| 0.9469	| 0.0000	| 0.9469	| 0.9482	| 0.9465	| 0.9317	| 0.9321	| 32.4460
rf	| Random Forest Classifier	| 0.8341	| 0.9792	| 0.8341	| 0.8458	| 0.8165	| 0.7843	| 0.7882	| 35.3740
dt	| Decision Tree Classifier	| 0.7587	| 0.8447	| 0.7587	| 0.7596	| 0.7586	| 0.6908	| 0.6910	| 20.6130
nb	| Naive Bayes	| 0.3833	| 0.6253	| 0.3833	| 0.4386	| 0.3946	| 0.2345	| 0.2404	| 8.3320



#### Regresión Logística
Las metrias que infican que este modelo tiene el mejor rendimiento con respecto a los demas.

- **Accuracy:** 94,69 % – Indica un alto porcentaje de clasificaciones correctas obtenidas por el modelo.
- **Precision y Recall:** Ambas metricas cuentan con un valor similar, lo que significa que el rendimiento encontro una mayor cantidad de verdaderos positivos sin muchos falsos positivos.
- **F1-Score:** 94,65 % – Garantiza un equilibrio entre precision y recall.
- **Kappa y MCC:** 93 % – Ambas metricas cuentan con un valor similar, lo que significa que hay concordancia entre las predicciones y las etiquetas verdaderas.
- **Training Time:** 32.45 sec – Razonable

- **AUC:** 0,0000 % - probablemente debido a los requisitos de clasificación binaria para ROC; PyCaret podría haber omitido el cálculo de esto para objetivos de múltiples clases.


#### Árbol de Decisión
Demuestra ser un buen modelo despues del Logistic Regression.

- **Accuracy:** 83.41% - indica que existe errores en la clasification.
- **AUC:** (0.9792) - muestra una gran capacidad para distinguir entre clases.
- **Precision y Recall:** (~84.58% y 83.41%), existe sierto equilibrio pero no se compara con el modelo Logistic Regression.
- **Training Time:** 35.3740 sec - similar al Logistic Regression pero le toma un poco mas de tiempo.

#### Bosque Aleatorio
Este resulta ser moderado en comparación con otros modelos

- **Accuracy:** 75.87% - el porcentaje va decanyendo con respecto al modelo Logistic Regression y Random Forest.
- **AUC:** 0.84% - cuenta con un buen porcentaje de clasificacion.
- **Precision y Recall:** (~75.96% and 75.87%) - bastante equilibrado pero menor a los modelos previos.
- **Training Time:** 20.61 sec - el tiempo es mejor que los anteriores modelos.

#### Naive Bayes
Sus metricas no son las mejores.

- **Accuracy:** 38.33% - el rendimiento esta por debajo del 50%. lo que demuestra que es malo.
- **AUC:** 0.6253 - refleja una mala discriminación entre clases.
- **Precision, Recall, F1:** todas debajo del 50% - indica una alta tasa de error en las predicciones.
- **Training Time:** 8.33 sec - el tiempo de entrenamiento es el mejor que el resto.

