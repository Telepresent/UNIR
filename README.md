# Proyecto FINTECH UNIR

El flujo de personas en la ciudad es objeto de un creciente interés por parte de empresas y administraciones. Esto se debe a que las dinámicas de la ciudad inciden en su economía. Por ejemplo, las cadenas comerciales, querrán abrir nuevos establecimientos en aquellos emplazamientos que presenten un mayor flujo de personas con perfil de potenciales clientes. Así mismo, la dinámica de las ciudades influye en la movilidad (ej demanda de taxi, Uber…) o la necesidad de infraestructuras e inversiones públicas entre otras cuestiones. La ciudad de Melbourne en Australia dispone de un sistema de aforamiento con datos abiertos http://www.pedestrian.melbourne.vic.gov.au/ que utilizaremos para la siguiente actividad.  

[![VIDEO ROBOT](images/Melbourne.jpg)](http://www.pedestrian.melbourne.vic.gov.au/)



* Descarga datos de flujo de personas en Melbourne de uno o varios meses en formato .csv (o se los puedo proporcionar yo mismo ya descargados).

* El sistema de monitorización de flujo de personas, se inicia como un proyecto piloto en el centro de la ciudad y se espera escalarlo a toda la ciudad (4,9 millones de habitantes). Explica las ventajas o desventajas de utilizar una base de datos SQL/NoSQL para ello. 

* Importa los datos .csv a MongoDB (puedes utilizar la interfaz gráfica Studio 3T que veremos en clase).

* Lanza las queries necesarias para determinar:

-¿En qué calle situarías un negocio que abre todos los días de 10:00h a 21:00h?

-La zona con menor flujo medio de personas para implementar medidas que potencien la zona. 

-…

* Una de las aplicaciones interesantes puede ser analizar el impacto económico de los eventos deportivos en una ciudad (ej. impacto partidos del Athletic en Bilbao https://www.tactizity.com/bilbao, https://reunir.unir.net/handle/123456789/6961 ) o hacer una previsión de la demanda de taxis http://www.smartaxi.me/ entre otras. ¿Qué aplicación se te ocurre que resultaría de interés para tu ciudad?















# App
## Cómo inicializar
Run `npm install`

Para ejecutarlo en tu móvil (conectador por USB), ejecutar:
Run `ionic cordova run android`


Para ver si él móvil está conectado, ejecutar
Run `adb devices`

