# CFE-IA-E7

## ChallengueNoticias 📰

### Este proyecto utiliza un conjunto de datos de oradores y noticias para predecir etiquetas asociadas a declaraciones públicas, en función de variables como el orador, el estado, el tema y la afiliación política.

## Objetivo

### Entrenar un modelo de clasificación que prediga la Etiqueta de una noticia o declaración según características del contexto político y del orador, y generar un archivo CSV con las predicciones finales.

## Datos

## Variables utilizadas en el modelo:

### Cantidad Verdadera: número de afirmaciones verdaderas asociadas al orador.

### Afiliación Política: categoría codificada según la orientación o grupo político.

### Estado: estado o región asociada al orador o declaración.

### Etiqueta: variable objetivo que representa la clasificación final del discurso (0 = falsa, 1 = verdadera, etc.).

# Pasos realizados

### Carga y preprocesamiento de datos

### Se cargaron los datasets df_train.csv y df_test_sin_etiqueta.csv.

### Se analizaron las columnas con valores vacíos y se reemplazaron por 0 o se eliminaron columnas irrelevantes:

### Cargo del Orador

# Contexto

### Se codificaron las variables categóricas mediante mapeos manuales:

### Afiliación Política → valores numéricos del 1 al 10 según categoría.

### Tema → valores del 1 al 5 (por ejemplo, salud, impuestos, energía, etc.).

### Estado y Orador → valores numéricos específicos por cada nombre.

### Se eliminaron filas duplicadas para asegurar la integridad del dataset.

### Se normalizaron las variables con StandardScaler para mejorar el rendimiento del modelo.

# Análisis exploratorio

### Se realizó un mapa de calor (heatmap) con seaborn para visualizar la correlación entre las variables más importantes:
Orador, Estado, Tema, Afiliación Política, Cantidad Verdadera, Cantidad Falsa, y Etiqueta.

## Entrenamiento del modelo KNN

## Se seleccionaron como características:
Cantidad Verdadera, Afiliación Política y Estado.

### Se utilizó train_test_split con un 20% de datos para validación.

### Se entrenó un modelo KNeighborsClassifier con k=5.

### Se calculó la exactitud (accuracy) sobre el conjunto de validación para evaluar el rendimiento del modelo.

## Predicciones y generación de submission

### Se aplicó el mismo preprocesamiento al conjunto de prueba (df_test_sin_etiqueta.csv).

### Se generaron las predicciones de etiquetas con el modelo entrenado.

## Se creó el archivo archivoCSV.csv con las columnas:

### ID

### Etiqueta

### Resultados

El promedio en el modelo fue de 60%

El modelo alcanza un nivel de exactitud satisfactorio para una primera aproximación.
El archivo archivoCSV.csv está listo para ser utilizado o presentado como salida del modelo.
