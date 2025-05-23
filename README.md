# Ride_hailing_app_trips_analysis
## Analisis de viajes realizados en una app de servicio de viajes
DA-7

## Descripción del proyecto
Estás trabajando como analista para Zuber, una nueva empresa de viajes compartidos que se está lanzando en Chicago. 

## Objetivo
Encontrar patrones en la información disponible. Comprender las preferencias de los pasajeros y el impacto de los factores externos en los viajes.
Al trabajar con una base de datos, se analizarán los datos de los competidores y se probará una hipótesis sobre el impacto del clima en la frecuencia de los viajes.

## Descripción de los datos
Una base de datos con información sobre viajes en taxi en Chicago:

### tabla neighborhoods: datos sobre los barrios de la ciudad

### name: nombre del barrio
- neighborhood_id: código del barrio
- tabla cabs: datos sobre los taxis

### cab_id: código del vehículo
- vehicle_id: ID técnico del vehículo
- company_name: la empresa propietaria del vehículo
- tabla trips: datos sobre los viajes

### trip_id: código del viaje
- cab_id: código del vehículo que opera el viaje
- start_ts: fecha y hora del inicio del viaje (tiempo redondeado a la hora)
- end_ts: fecha y hora de finalización del viaje (tiempo redondeado a la hora)
- duration_seconds: duración del viaje en segundos
- distance_miles: distancia del viaje en millas
- pickup_location_id: código del barrio de recogida
- dropoff_location_id: código del barrio de finalización
- tabla weather_records: datos sobre el clima

### record_id: código del registro meteorológico
- ts: fecha y hora del registro (tiempo redondeado a la hora)
- temperature: temperatura cuando se tomó el registro
- description: breve descripción de las condiciones meteorológicas, por ejemplo, "lluvia ligera" o "nubes dispersas"

## Esquema de la tabla
![ver imagen](table_diagram.png)

Nota: no existe una conexión directa entre las tablas trips y weather_records en la base de datos. Pero se puede usar JOIN y vincularlas usando la hora en la que comenzó el viaje (trips.start_ts) y la hora en la que se tomó el registro meteorológico (weather_records.ts).

Además de los datos recuperados en las tareas anteriores, se tiene un segundo archivo. Ahora se tienen estos dos CSV:

### project_sql_result_01.csv. Contiene los siguientes datos:

- company_name: nombre de la empresa de taxis
- trips_amount: el número de viajes de cada compañía de taxis el 15 y 16 de noviembre de 2017.

### project_sql_result_04.csv. Contiene los siguientes datos:

- dropoff_location_name: barrios de Chicago donde finalizaron los viajes
- average_trips: el promedio de viajes que terminaron en cada barrio en noviembre de 2017.

### project_sql_result_07.csv: el resultado de la última consulta. Contiene datos sobre viajes desde el Loop hasta el Aeropuerto Internacional O'Hare. Recuerda, estos son los valores de campo de la tabla:

- start_ts: fecha y hora de recogida
- weather_conditions: condiciones climáticas en el momento en el que comenzó el viaje
- duration_seconds: duración del viaje en segundos

![Ver queries](SQL%20queries%20DA-7.txt)

![Ver recopilación de datos de clima NOV 2017](Website%20data%20collection.txt)



