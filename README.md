# Práctica indiviual de Kaggle - Big Five Personality Test

## Nombre: Harold André Gonzales Contreras
## NIU: 1571485
## Contacto: 1571485@uab.cat
## Caso Kaggle:
_El objetivo con esta base de datos es predecirlas cinco grandes personalidades que tiene una persona en base a un test realizado, y gracias a los resultados dados (respuestas entre 0 y 5) poder decir si una persona es inventivo vs. consistente, organizado vs extravagante, sociable vs. solitario, amigable vs. desafiante, y  nervioso vs. seguro._
[Base de datos de Kaggle](https://www.kaggle.com/datasets/tunguz/big-five-personality-test?resource=download)

## Resumen
La base de datos del caso Kaggle "Big Five Personality Test" dispone de 110 atributos/columnas, donde las primeras 50 columnas representan las respuestas de las personas, las siguientes 50 columnas (que acaban con un "_ E" al final del atributo) representan el tiempo de respuesta y los 10 siguientes atributos son informaciones extras. Hay 5 campos que estudiaremos (Extraversion, Agreeableness, Neuroticism, Conscientiousness, Openness to experience) y cada una tiene su propia etiqueta (EXT, AGR, EST, CSN, OPN respectivamente). Cada campo tiene 10 propias etiquetas (EXT1, EXT2, etc...) y cada respuesta tiene un valor entre 0 y 5.


## Objetivo del dataset
Utilizar varios modelos de aprendizaje para saber cuál es el mejor para nuestra base de datos y en sus características. Y analizar los datos para optimizar ese proceso.


## Experimentos
Para entender mejor la base de datos primero se analizaron y visualizaron los datos, después se vieron las correlaciones y las distribuciones de las variables para tomar una decisión de qué hacer con la base de datos para encontrar una solución.


### Preprocesado
Primero se hizo un análisis de los datos para ver si existen datos con valores nulos y repetidos para depurarlo y así tener menos trabajo en un futuro.

Luego con un Heatmap se vio las correlaciones de las variables, como podemos observar en la siguiente imagen:
![heatmap](https://user-images.githubusercontent.com/57755402/207672524-58182634-be4d-4157-907c-675232b7d752.png)

Podemos comprobar que EXT (Extroversion) y AGR (Agreeableness) tienen un valor más alto que los demás, por tanto podemos decir que tienen mayor correlación. Sin embargo, podemos visualizar valores negativos de EST (Neuroticism) con EXT (-0.22) y CSN (Conscientiousness, -0.23).
De acuerdo con el libro de códigos, las latitudes y longitudes dadas (columnas lat_appx_lots_of_err y long_appx_lots_of_err) son muy inexactas, por lo que se eliminarán ambas columnas. Además, he pasado los tipos de respuesta a integers.
Algunos tiempos son excesivos o hay algunos negativos, por lo que aceptamos solamente un tiempo maximo de 30 segundos y un mínimo de 0.

### Modelo

|  | CV Score |
| ------------- | ------------- |
| KNN  | 42.9%  |
| Decision Tree  | 44,7%  |
| Logistic Regression  | 57.1%  |
| SVM  | 57%  |

## Conclusiones
A través de esta EDA, estudiamos el conjunto de datos en diferentes aspectos: tiempos de respuesta, series temporales, análisis geográfico (continentes, países). Podemos explorar más y explotar mejor la información de este conjunto de datos haciendo coincidir los datos sociodemográficos. En ese caso se pueden hacer regresiones. Además, se podrían aplicar algoritmos no supervisados a este conjunto de datos para descubrir grupos. De acuerdo con los resultados obtenidos, podríamos dar una descripción de cada clúster para que las personas puedan verse a sí mismas a través de los resultados.

He hecho varias pruebas utilizando varios tamaños de la base de datos y modificando los modelos de aprendizaje, y en todos los **Logistic Regression y SVM** siempre daban los mejores resultados.


## Licencias
Este Notebook ha sido lanzado bajo la licencia de código abierto **Apache 2.0**.
