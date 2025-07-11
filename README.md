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


Al comenzar, cargamos los datos y realizamos cierta limpieza en ellos, eliminando características irrelevantes como nombres, fechas de nacimiento y datos contractuales que no aportaban valor predictivo, también hicimos matrices de correlación solo para que ver que tan relacionados estaban ciertas caracteristicas. 

Luego de eso, partimos de lleno con el entrenamiento, en donde conjunto de datos se preparó separando las características predictoras (X) de la variable objetivo 'potential' (y), dividiéndose en grupos de entrenamiento (80%) y prueba (20%). Las variables se estandarizaron mediante StandardScaler para normalizar sus escalas, y como se mencionó anteriormente, se implementaron dos modelos predictivos: un Árbol de Decisión (con profundidad máxima de 5) y un Random Forest (con 100 estimadores), ambos configurados con random_state=42 para reproducibilidad. Los modelos se entrenaron con los datos estandarizados y se evaluaron mediante las métricas clave mencionadas (RMSE, MAE y R²) en el conjunto de prueba, permitiendo comparar objetivamente su rendimiento en la predicción del potencial de los jugadores

Los modelos demostraron una capacidad predictiva significativa para estimar el potencial de jugadores. El Random Forest superó claramente al Árbol de Decisión, con un MAE 53% más preciso y un R² de 0.963, indicando que explica el 96% de la variabilidad en los datos. Las gráficas de predicción vs valores reales muestran una alta correlación, aunque se observan ligeras subestimaciones en jugadores de alto potencial (>85 puntos). El análisis de importancia de características reveló que atributos técnicos como ball_control y dribbling son los principales predictores, alineándose con el conocimiento experto en fútbol. Estos resultados validan la utilidad del modelo para aplicaciones prácticas como scouting y valoración de jugadores, aunque se recomienda ajustar el modelo para reducir el sesgo en predicciones de alto rango. Los detalles completos del análisis exploratorio, implementación y métricas están disponibles en el notebook adjunto.

A partir del análisis realizado, se logró construir modelos predictivos que permiten estimar con buena precisión el potencial futuro de jugadores de fútbol en base a sus atributos actuales. El modelo de Random Forest destacó por su capacidad de generalización y su robustez frente a datos ruidosos, superando al árbol de decisión individual en métricas clave como MAE, RMSE y R². Además, se pudo identificar qué características influyen más en el desarrollo proyectado de un jugador, lo cual entrega información valiosa para procesos de scouting o evaluación de talento.




