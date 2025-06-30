# Proyecto_IA
Matín Reyes y Felipe Cabezas

Dataset: Football Players Data (https://www.kaggle.com/datasets/maso0dahmed/football-players-data/data)

Elección del problema: Con la disponibilidad de datos que se tiene hoy en día,
resulta una gran oportunidad el usar herramientas que nos permita determinar tanto el rendimiento
como el potencial de cada jugador. Teniendo en cuenta que este dataset nos proporciona diversos 
atributos de una gran cantidad de jugadores, se abre la posibilidad de crear un modelo de regresión 
que prediga el potencial de cada jugador. Para esto, usaremos los distintos métodos vistos en clase.SS

Para abordar el problema de predicción del rendimiento futuro de jugadores a partir de sus atributos, 
es conveniente utilizar modelos  como los Árboles de Decisión y Random Forest, debido a varias razones
técnicas y prácticas.

En primer lugar, estos modelos son especialmente eficaces cuando se trabaja con datos tabulares, como el
que se dispone en este caso (con cerca de 17.000 registros de jugadores), ya que pueden manejar tanto 
variables numéricas como categóricas sin necesidad de transformaciones complejas. Además, no requieren  
una relación lineal entre las variables predictoras y la variable objetivo, lo que los hace adecuados 
para capturar relaciones no lineales y patrones complejos presentes en los atributos de rendimiento de 
los jugadores.

Por otro lado, los árboles de decisión son fáciles de interpretar y permiten visualizar cómo se toman las
decisiones, lo que es útil para entender qué factores influyen más en el rendimiento futuro. Sin embargo,
al ser modelos propensos al sobreajuste, se propone también el uso de Random Forest, un modelo de conjunto 
que combina múltiples árboles y reduce significativamente la varianza del modelo individual, mejorando así
la precisión y generalización sobre nuevos datos. Estos algoritmos son robustos ante datos ruidosos y pueden
manejar grandes volúmenes de información, por lo que representan una opción balanceada entre interpretabilidad,
rendimiento y facilidad de implementación para una primera aproximación al problema predictivo.
