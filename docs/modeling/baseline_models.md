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

## Evaluación del modelo

### Métricas de evaluación

La métrica principal usada para la evaluación del modelo son:
- Accuracy: que calcula la proporción de predicciones correctas sobre el total de observaciones

Probamos otras métricas como F1 score, precisión y recall. Sin embargo, estas métricas nos dan 0. Esto se debe a que existe un fuerte desbalanceo en los datos, debido a que son muy pocos los vuelos atrasados en comparación con los no atrasados. Para solucionar este problema debemos retroceder unos pasos y usar métodos oversalmpling de la clase minoritaria o el ajuste de los pesos de las clases. Sin embargo, por temas de tiempo realizaremos esta corrección para la siguiente etapa.

### Resultados de evaluación

Accuracy | F1 score | Precisión | Recall


## Análisis de los resultados

Descripción de los resultados del modelo baseline, incluyendo fortalezas y debilidades del modelo.

## Conclusiones

Conclusiones generales sobre el rendimiento del modelo baseline y posibles áreas de mejora.

## Referencias

Lista de referencias utilizadas para construir el modelo baseline y evaluar su rendimiento.

Espero que te sea útil esta plantilla. Recuerda que puedes adaptarla a las necesidades específicas de tu proyecto.
