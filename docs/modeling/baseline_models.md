# Reporte del Modelo Baseline

## Descripción del modelo

Teniendo en cuenta que lo que buscamos con nuestros modelos es predecir qué vuelos van a llegar atrasados y cuales no, es decir, basicamente una tarea de clasificación, nuestro modelo baseline va a ser una regresión logística. De esta forma, a partir de las distintas características de los vuelos, el modelo nos brindará la probabilidad de que estos lleguen atrasados o no.

## Variables de entrada

- Airline                   
- Origin
- Dest                 
- CRSDepTime         
- DepTime                  
- DepDelayMinutes          
- DepDelay            
- ArrTime         
- ArrDelayMinutes          
- AirTime                      
- CRSElapsedTime             
- ActualElapsedTime        
- Distance                 
- Year                    
- Month                       
- DayofMonth                 
- DayOfWeek                   
- Operated_or_Branded_Code_Share_Partners 
- DOT_ID_Marketing_Airline          
- Flight_Number_Marketing_Airline      
- Operating_Airline               
- DOT_ID_Operating_Airline        
- Tail_Number                    
- Flight_Number_Operating_Airline       
- OriginAirportID          
- OriginAirportSeqID      
- OriginCityMarketID        
- OriginCityName  
- OriginState                  
- OriginStateFips                
- OriginWac                   
- DestAirportID            
- DestAirportSeqID     
- DestCityMarketID           
- DestCityName        
- DestState                   
- DestStateFips            
- DestStateName                  
- DestWac                        
- DepDel15                
- DepartureDelayGroups         
- DepTimeBlk                
- TaxiOut                        
- WheelsOff                      
- WheelsOn                           
- TaxiIn                            
- CRSArrTime
- DistanceGroup

Teniendo en cuenta la gran cantidad de variables, así como el gran número de observaciones, se utiliza componentes principales (3).

## Variable objetivo

La variable objetivo es Arr_Delayed, la cual es una variable binaria que indica si el vuelo llegó atrasado (1) o a tiempo (0). 

Se observa que existe un desbalanceo en esta variable; existen pocas observaciones para las cuales Arr_Delayed = 1, es decir, pocos vuelos llegaron atrasados. Por ello, se generaron observaciones sintéticas de vuelos atrasados por medio de SMOTE para evitar problemas con los modelos.

## Evaluación del modelo

### Métricas de evaluación

Las métricas principales usadas para la evaluación del modelo son:
- Accuracy: que calcula la proporción de predicciones correctas sobre el total de observaciones.
- Precision: que es la proporción de predicciones positivas correctas.
- Recall: proporción de predicciones correctas entre todas las predicciones.
- F1 Score: la media armónica entre la precisión y el recall.

### Resultados de evaluación

| Accuracy | F1 score | Precisión | Recall|
|------|---------|-------|-------| 
| 0.521569 | 0.273979 | 0.192294 | 0.476308 |

## Análisis de los resultados

En general las métricas muestran que el modelo no presenta un buen desempeño. El accuracy indiica que el modelo tiene problemas para capturar patrones de los datos, mientras que el F1 score, la precisión y el recall indican que tiene problemas para predecir correctamente las observaciones de la clase positiva.

La principal fortaleza del modelo es que es un modelo sencillo, fácil de interpretar y eficiente computacionalmente. Sin embargo, en parte esta también es su mayor debilidad, ya que el modelo no es capaz de capturar relaciones complejas (por ejemplo, no lineales) en los datos, lo que explica los pobres resultados de las métricas.

## Conclusiones

En general el modelo baseline tiene dificultades para manejar los datos, y por ello es poco confiable al momento de predecir si un vuelo estará o no atrasado. Por ello, la principal área de mejora radica en utilizar otros modelos capaces de capturar más adecuadamente las relaciones complejas en los datos.

## Referencias

modelo: https://scikit-learn.org/1.5/modules/linear_model.html
métricas: https://scikit-learn.org/1.5/api/sklearn.metrics.html
