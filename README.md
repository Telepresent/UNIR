# Proyecto FINTECH UNIR

El flujo de personas en la ciudad es objeto de un creciente interés por parte de empresas y administraciones. Esto se debe a que las dinámicas de la ciudad inciden en su economía. Por ejemplo, las cadenas comerciales, querrán abrir nuevos establecimientos en aquellos emplazamientos que presenten un mayor flujo de personas con perfil de potenciales clientes. Así mismo, la dinámica de las ciudades influye en la movilidad (ej demanda de taxi, Uber…) o la necesidad de infraestructuras e inversiones públicas entre otras cuestiones. La ciudad de Melbourne en Australia dispone de un sistema de aforamiento con datos abiertos http://www.pedestrian.melbourne.vic.gov.au/ que utilizaremos para la siguiente actividad.  

[![VIDEO ROBOT](images/Melbourne.jpg)](http://www.pedestrian.melbourne.vic.gov.au/)



# Firmware del robot para Microbit

El firmware del robot para la tarjeta Microbit se ha desarrollado en lenguaje MicroPyhon. A continuación se describen algunos puntos clave del código. 

# App
## Cómo inicializar
Run `npm install`

Para ejecutarlo en tu móvil (conectador por USB), ejecutar:
Run `ionic cordova run android`


Para ver si él móvil está conectado, ejecutar
Run `adb devices`


* •	Descarga datos de flujo de personas en Melbourne de uno o varios meses en formato .csv (o se los puedo proporcionar yo mismo ya descargados).

* •	El sistema de monitorización de flujo de personas, se inicia como un proyecto piloto en el centro de la ciudad y se espera escalarlo a toda la ciudad (4,9 millones de habitantes). Explica las ventajas o desventajas de utilizar una base de datos SQL/NoSQL para ello. 

* •	Importa los datos .csv a MongoDB (puedes utilizar la interfaz gráfica Studio 3T que veremos en clase).

* •	Lanza las queries necesarias para determinar (tengo que ver para calibrar la dificultad):

-¿En qué calle situarías un negocio que abre todos los días de 10:00h a 21:00h?

-La zona con menor flujo medio de personas para implementar medidas que potencien la zona. 

-…

* •	Una de las aplicaciones interesantes puede ser analizar el impacto económico de los eventos deportivos en una ciudad (ej. impacto partidos del Athletic en Bilbao https://www.tactizity.com/bilbao, https://reunir.unir.net/handle/123456789/6961 ) o hacer una previsión de la demanda de taxis http://www.smartaxi.me/ entre otras. ¿Qué aplicación se te ocurre que resultaría de interés para tu ciudad?



* .env.prod
* .env.dev

# Backend

## Cómo inicializar
Hacer una copia de backend/docker/.env.example y renombrarlo a .env y asignar los valores adecuados Estos deben corresponderse con los archivos .env de la App. 

# Medición de CO2 en el aula y visualización con Node-Red

## Dashboard en Node-Red
Se ha desarrollado un firmware para un microcontrolador Particle.io que lee de un sensor DHT11 de temperatura y humedad y un sensor CCS811 de eCO2 y VOC. Los datos recogidos se pueden visualizar en el siguiente enlace: 

* [Dashboard](https://j6q00k.stackhero-network.com/dashboard/)
 

"Algunos científicos comentan que mejorar la ventilación y la calidad del aire es un método que las escuelas pueden usar para reducir el riesgo de transmisión del coronavirus. Sin embargo, en una encuesta entre distritos escolares grandes del Norte de Texas, The Dallas Morning News encontró que las escuelas están lejos de alcanzar los parámetros de calidad del aire propuestos en junio por expertos en construcción. Investigadores de la Universidad de Harvard recomendaron instalar filtros de aire de alta graduación, limpiadores de aire portátiles y fuentes de luz ultravioleta dentro de los conductos de aire para eliminar al virus. Al revisar el nivel de dióxido de carbono en las aulas se puede comprobar si está entrando suficiente aire fresco..."
 
Fuente: https://noticiasenlafrontera.net/escuelas-no-siguen-recomendaciones-de-calidad-del-aire-parar-reducir-exposicion-a-covid-19/

Existen además evidencias de que los altos niveles de CO2 influyen sobre el rendimiento de los alumnos en el aula. https://pubmed.ncbi.nlm.nih.gov/25117890/

## Multisensor
[![Sensor](img/Sensor.jpg)](https://www.youtube.com/watch?v=9LAC98Wxa0o)


* Temperatura
* Humedad ambiente
* eCO2
* VOCs en el aire 
* Ruido
* Movimiento (PIR) 
* Iluminación

# Diseño mecánico del robot para impresión 3D y Realidad Aumentada

Se puede visualizar el robot en Realidad Aumentada, escaneando el siguiénte código QR. 


[![QR](img/2.png)](https://sketchfab.com/3d-models/robot-de-telepresencia-imh-ce46d0bd06b64048968173223d61c20a)

# Proceso de fabricación
El proceso de fabricación se simula utilizando un PLC S7-1200 de SIEMENS y el software Factory.io

*  Proceso separación del empaquetado para su envío.
*  Proceso de clasificación de piezas.
 


# Créditos

La información sobre Robbit se encuentra disponible en  https://www.robbit.se creado por el instituto sueco RISE. 

Modelos 3D del proyecto https://www.thingiverse.com/thing:3360113

Using the sound Open Button 2 by Kickhat with creative commons 0 license.
https://freesound.org/people/kickhat/sounds/264447/

Using the sound Correct by Ertfelda with creative commons 0 license.
https://freesound.org/people/ertfelda/sounds/243701/


