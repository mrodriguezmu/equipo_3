# Informe de salida

## Resumen Ejecutivo

Durante este proyecto se buscó, por medio de distintos métodos y modelos, predecir de forma precisa qué vuelos llegarían atrasados, a partir de distintas caracteristicas de los mismos. Por medio de una rica base de datos, se procuró procesar los mismos para poder manejarlos de la forma más eficiente posible, tal que se pudieran utilizar distintos modelos como regresión logistica, Random Forest y Gradient Boosting para relizar predicciones. En últimas, el modelo final fue Random Forest, ya que presentó el mejor desempeño en métricas como accuracy, presición, recall y F1 score.

## Resultados del proyecto

- Resumen de los entregables y logros alcanzados en cada etapa del proyecto.
  
A lo largo de las distintas etapas recuperamos la rica base de datos de la página kaggle, revisando las múltiples variables con las que contabamos (tipo de aeronave, ciudad y tiempo de salida, ciudad y tiempo de llegada, fecha, etc), para entender cuáles podiamos útilizar para nuestro propósito, cuáles no, y qué transformaciones debian realizarse para utilizarlos de la forma más eficiente posible.
Igualmente, dada la gran cantidad de variables explicativas, utilizamos componentes principales antes de entrenar los modelos, para así poder mejorar la eficiencia computacional. Apartir de allí establecimos un modelo baseline, el cual fue regresión logística. Lo comparamos con otros dos modelos, Random Forest y Gradient Boosting, llegando a la conclusión que el mejor modelo fue Random Forest.
Finalmente, realizamos el despliegue del modelo por medio de Flask, tal que fuera posible para un usuario proveer caracteristicas específicas de un vuelo para predecir si este llegaria con retraso o no. 

- Evaluación del modelo final y comparación con el modelo base.
  
El modelo final, es decir, el Random Forest presentó las siguientes métricas:
| Accuracy | F1 score | Precisión | Recall|
|------|---------|-------|-------| 
| 0.756662 | 0.396130 | 0.373940 | 0.421120 |

Vemos que cada una de ellas (con excepción de recall) es mayor a las métricas del modelo base (regresión logistica):
| Accuracy | F1 score | Precisión | Recall|
|------|---------|-------|-------| 
| 0.521569 | 0.273979 | 0.192294 | 0.476308 |

- Descripción de los resultados y su relevancia para el negocio.

El modelo en general presenta un desempeño moderado. El accuaracy indica que la gran mayoria de las predicciones fueron correctas. Sin embargo, el F1 score, la precisión y el recall indican que tiene ciertos problemas para predecir correctamente los vuelos atrasados. Enn general, teniendo en cuenta el objetivo principal del negocio, se pueden considerar estos resultados como aceptables, ya que permite predecir, hasta cierto punto, qué vuelos llegaran atrasados y qué vuelos no. De esta forma, se puede usar esta herramienta como un complemento (no como definitiva) en la industria aeronautica. 

## Lecciones aprendidas

- Identificación de los principales desafíos y obstáculos encontrados durante el proyecto.
  
A lo largo del proyecto, se presentaron dos obstáculos principales: el primero de ellos es la gran cantidad de información con la que se cuenta. Dada la gran extensión de la base de datos original (millones de observaciones y más de 50 variables) fue necesario omitir información en pro de la eficiencia computacional. Por ello nos vimos obligados a trabajar con menos del 5% de la información total de la que disponiamos, solamente para que nuestros equipos pudieran procesar los datos. Esto también afecto los modelos utilizados, ya que, por ejemplo, quisimos utilizar más modelos como support vector machines, pero no fue posible debido a los prolongados tiempos para correr los códigos.

El segundo gran problema, derivado del ya mencionado, es el desbalance en la variable objetivo; contabamos con muy pocos datos de vuelos atrasados, lo cual generó que nuestros primeros modelos fueran casi que obsoletos. Para ello tuvimos que generar datos sintéticos de vuelos atrasados, lo cual en últimas permitió que que los modelos fueran aplicables, pero que isn duda afectó su desempeño.

- Lecciones aprendidas en relación al manejo de los datos, el modelamiento y la implementación del modelo.
  
Loa lección principal es que, cuando se quiere trabajar con grandes volúmenes de información, pero no se cuenta con los equipos necesarios para ello, es necesario aplicar métodos que sean capaces de procesar los datos de forma eficiente sin perder la mayor cantidad de información posible (como componentes principales). Igualmente, estas relaciones complejas de los datos hacen que la selección del modelo deba ser cuidadosa, ya que si bien se puden implementar modelos más sencillos, que a su vez serán más eficientes, estos pueden no capturar las relaciones adecuadas de los datos y por ello prsentar buenos desempeños. Mientras que, otros modelos que si son capaces de capturar estas relaciones, pueden ser demasiados complejos y poco eficientes computacionalmente.

Por ello hay que encontrar un equilibrio entre eficiencia y desempeño.

- Recomendaciones para futuros proyectos de machine learning.
  
Trabajar los datos de forma más eficiente desde el principio, y tal vez centrarse en conjuntos de datos menos complejos y que se puedan adaptar mejor al equipo del que uno disponga, para sacar el mayor provecho a la información disponible.

## Impacto del proyecto

- Descripción del impacto del modelo en el negocio o en la industria.
  
Si bien el modelo no presenta un desempeño excepcional, si se puede usar como una herramienta complementaria en la industria aeronautica, así como para los clientes de la misma, al momento de predecir qué vuelos llegaran o no atrasados. Esto para poder optimizar, por ejemplo, rutas de vuelo y mejorar el flujo del tráfico aério y aeroportuario. 

- Identificación de las áreas de mejora y oportunidades de desarrollo futuras.
  
A futuro, lo ideal seria poder trabajar con la totalidad de los datos, de forma que se puedan capturar las relaciones de los datos de forma más precisa y poder implementar modelos muchos más complejos. Esto permitirá sin duda alguna realizar predicciones mucho más precisas y confliables.

## Conclusiones

- Resumen de los resultados y principales logros del proyecto.
  
El principal logro de este proyecto es que, si bien no se realizaron predicciones tan precisas como se esperaba, si se logró obtener un modelo con un desempeño aceptable, logro que es aun más importante al tener en cuenta las grandes limitaciones brindadas por los datos y por los equipos con los que se contaba.

- Conclusiones finales y recomendaciones para futuros proyectos.
  
El modelo de Random Forest es el más adecuado para predecir qué vuelos llegaran atrasados y qué vuelos no. Este modelo presenta un buen desempeño en cuanto a predicciones generales, aunque tiene dificultades para predecir correctamente los vuelos atrasados (más que los puntuales). Para futuros proyectos, se debe trabajar los datos de forma más eficiente y, de ser posible, contar con mejores equipos para implementar modelos más complejos, aprovechar al máximo la información disponible y poder realizar predicciones mucho más confiables.

