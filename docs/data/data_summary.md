# Reporte de Datos

Este documento contiene los resultados del análisis exploratorio de datos.

## Resumen general de los datos

En esta sección se presenta un resumen general de los datos. Se describe el número total de observaciones, variables, el tipo de variables, la presencia de valores faltantes y la distribución de las variables.

Se presentan en la data del año 2018 
Número total de observaciones: 5689512
Número total de variables: 61
Variables categoricas, booleanas y númericas
Se presentan faltantes en aproximadamente 102893 observaciones 

## Resumen de calidad de los datos

En esta sección se presenta un resumen de la calidad de los datos. Se describe la cantidad y porcentaje de valores faltantes, valores extremos, errores y duplicados. También se muestran las acciones tomadas para abordar estos problemas.

La Cantidad de valores faltantes son de 102.893 en su maxima variable que representan al 1.8% de los datos
No presenta valores duplicados
y Teniendo enc uenta como extremo 60 minutos, se presentan 354751 veces

## Variable objetivo

En esta sección se describe la variable objetivo. Se muestra la distribución de la variable y se presentan gráficos que permiten entender mejor su comportamiento.

Nuestra variable objetivo va a ser ArrDelay (Diferencia en minutos entre la hora de llegada programada y la hora de llegada real. Las llegadas tempranas muestran números negativos.) 

![image](https://github.com/user-attachments/assets/af72f404-889f-44e9-9783-b6ddd8540e6a)

Su valor Maximo es de 2635 y minimo de -1290, en promedio los datos tienen una hora de retraso en llegada en 5.41 minutos


## Variables individuales

En esta sección se presenta un análisis detallado de cada variable individual. Se muestran estadísticas descriptivas, gráficos de distribución y de relación con la variable objetivo (si aplica). Además, se describen posibles transformaciones que se pueden aplicar a la variable.

Se presenta analisis de la variable DepDelay (Diferencia en minutos entre la hora de salida programada y la hora de salida real. Las salidas anticipadas muestran números negativos.)

![image](https://github.com/user-attachments/assets/75452036-0544-475a-89b4-d2e940f9afd9)

Su valor Maximo es de 2625 y minimo de -1280, en promedio los datos tienen una hora de retraso en salida en 10.14 minutos

## Ranking de variables

En esta sección se presenta un ranking de las variables más importantes para predecir la variable objetivo. Se utilizan técnicas como la correlación, el análisis de componentes principales (PCA) o la importancia de las variables en un modelo de aprendizaje automático.

De nuestras variables numericas presentan en correlacion con nuestra variable pbjetivo

Correlaciones con ArrDelay:
 ArrDelay                           1.000000
ArrDelayMinutes                    0.981821
DepDelay                           0.959378
DepDelayMinutes                    0.956559
ArrivalDelayGroups                 0.879513
DepartureDelayGroups               0.833875
ArrDel15                           0.615918
DepDel15                           0.575360
TaxiOut                            0.216379
DepTime                            0.130860
WheelsOff                          0.126356
TaxiIn                             0.103253
CRSDepTime                         0.095700
CRSArrTime                         0.083648
WheelsOn                           0.039117
ActualElapsedTime                  0.037455
DOT_ID_Operating_Airline           0.034716
DOT_ID_Marketing_Airline           0.033171
ArrTime                            0.032115
Flight_Number_Operating_Airline    0.018340
Flight_Number_Marketing_Airline    0.018302
DestStateFips                      0.008026
OriginStateFips                    0.002241
DestAirportID                      0.000360
DestAirportSeqID                   0.000360
AirTime                            0.000157
Quarter                           -0.000077
Month                             -0.000223
DestCityMarketID                  -0.002342
OriginAirportID                   -0.004218
OriginAirportSeqID                -0.004218
OriginCityMarketID                -0.008317
DayofMonth                        -0.009931
DayOfWeek                         -0.010573
OriginWac                         -0.013530
Distance                          -0.017161
DistanceGroup                     -0.017175
CRSElapsedTime                    -0.018970
DestWac                           -0.022842


## Relación entre variables explicativas y variable objetivo

En esta sección se presenta un análisis de la relación entre las variables explicativas y la variable objetivo. Se utilizan gráficos como la matriz de correlación y el diagrama de dispersión para entender mejor la relación entre las variables. Además, se pueden utilizar técnicas como la regresión lineal para modelar la relación entre las variables.

Para un analisis de la correlación que presenta la variable objetivo con la individual de retraso en el despegue 

![image](https://github.com/user-attachments/assets/7e7df46c-cc13-47d9-a9c4-cdb494eab813)


