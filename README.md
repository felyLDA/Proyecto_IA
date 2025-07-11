# Proyecto_IA
Matín Reyes y Felipe Cabezas

Dataset: Football Players Data (https://www.kaggle.com/datasets/maso0dahmed/football-players-data/data)

Elección del problema: Con la disponibilidad de datos que se tiene hoy en día,
resulta una gran oportunidad el usar herramientas que nos permita determinar tanto el rendimiento
como el potencial de cada jugador. Teniendo en cuenta que este dataset nos proporciona diversos 
atributos de una gran cantidad de jugadores y su respectivo potencial, se abre la posibilidad de crear un modelo de regresión 
que prediga el potencial de cada jugador. Para esto, usaremos los distintos métodos vistos en clase.

Para abordar el problema de predicción del rendimiento futuro de jugadores a partir de sus atributos, es conveniente utilizar modelos como los Árboles de Decisión y Random Forest, debido a varias razones técnicas y prácticas.

En primer lugar, estos modelos son especialmente eficaces cuando se trabaja con datos tabulares, como el que se dispone en este caso (con más de 17.000 registros), ya que pueden manejar tanto variables numéricas como categóricas sin necesidad de transformaciones complejas. Además, no requieren una relación lineal entre las variables predictoras y la variable objetivo, lo que los hace adecuados para capturar relaciones no lineales y patrones complejos presentes en los atributos de rendimiento de los jugadores.

El dataset contiene información de alrededor de 18.000 jugadores profesionales de fútbol, incluyendo:
-Atributos personales: nombre, edad, nacionalidad, altura, peso.
-Atributos físicos y técnicos: velocidad, fuerza, control del balón, regate, pase, entre otros.
-Atributos de valor: overall (nivel actual), potential (nivel estimado futuro).
El objetivo será predecir la variable continua potential utilizando como predictores
los atributos disponibles, descartando variables redundantes o no predictivas.

Se trabajará con los siguientes modelos de regresión, considerando que la variable que queremos predecir es continua:

-Decision Tree: fáciles de interpretar y permiten visualizar cómo se toman las decisiones

-Random Forest Regressor: para capturar relaciones no lineales y efectos de interacción entre atributos.
en clase se mencionó que algoritmos de decision tree eran adaptablen para realizar regresiones.

Los árboles de decisión son fáciles de interpretar y permiten visualizar cómo se toman las decisiones, lo que es útil para entender qué factores influyen más en el rendimiento futuro. Sin embargo, al ser modelos propensos al sobreajuste, se propone también el uso de Random Forest, un modelo de conjunto que combina múltiples árboles y reduce significativamente la varianza del modelo individual, mejorando así la precisión y generalización sobre nuevos datos. Estos algoritmos son robustos ante datos ruidosos y pueden manejar grandes volúmenes de información, por lo que representan una opción balanceada entre interpretabilidad, rendimiento y facilidad de implementación para una primera aproximación al problema predictivo.

Estrategia de Evaluación
La evaluación de los modelos se realizará a través de técnicas de validación cruzada, utilizando las siguientes 
métricas vistas en clase:

-MAE (Mean Absolute Error)
-RMSE (Root Mean Squared Error)
-R² (coeficiente de determinación)


Ventajas:

Ambos modelos (árbol y bosque aleatorio) funcionan bien con datasets tabulares como el presente.
Soportan relaciones no lineales entre variables.
No requieren escalamiento de variables ni normalización.
Son robustos frente a outliers y datos faltantes (especialmente Random Forest).
Permiten conocer la importancia relativa de cada atributo para la predicción.

Limitaciones:

Los árboles de decisión individuales tienden a sobreajustar, especialmente si no se limita su profundidad.
Random Forest, aunque más preciso, puede ser menos interpretable que un solo árbol.
Ambos modelos pueden ser menos efectivos si hay muchas variables irrelevantes o ruidosas (requieren una buena selección de características).
Pertinencia:
Estos modelos son adecuados para una primera aproximación al problema, ya que combinan buena capacidad predictiva con facilidad de implementación e interpretación.

Además, fueron revisados en clase y permiten reforzar conceptos clave como overfitting, importancia de atributos y evaluación de modelos de regresión, alineándose con los objetivos pedagógicos del proyecto.

