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














# SOLUCIÓN:

1.	En primer lugar tenemos que obtener los datos de flujo de personas con los que vamos a trabajar. Son los datos de enero a diciembre de 2017 y se pueden descargar de la web de la ciudad de Melbourne http://www.pedestrian.melbourne.vic.gov.au/

2.	Es necesario importar los documentos a MongoDB. Si tenemos 12 archivos .csv, tendríamos que ejecutar 12 veces el comendo. Para facilitar la tarea, he creado un único archivo, denominado “Result.csv” con los datos de los 12 meses. 

El comando a ejecutar para importar el documento .csv es: 

< mongoimport --db test --collection personas --type csv --file Result.csv --headerline


3.	Ya tenemos los datos en MongoDB, pero no están en el orden en el que nos gustaría en MongoDB. Podemos ordenarlos con el siguiente script. 


```javascript
function getDateStats(d, format = "", separator = "-", utc = false) {
    // print(d);
    if(d == undefined){
        return null;
    }
    if(typeof  d == 'string'){
        var parts = d.split(separator);
        if(format == 'ddmmyy'){
            var dd = new Date(parseInt(parts[2], 10), parseInt(parts[1], 10) - 1, parseInt(parts[0], 10));
        }else if(format == 'mmddyy'){
            var dd = new Date(parseInt(parts[2], 10), parseInt(parts[0], 10) - 1, parseInt(parts[1], 10));
        }
        else{
            var dd = new Date(d);
        }
    }else{
        var dd = new Date(d);
    }
    if(utc){
        var day = dd.getUTCDate();
        var month = dd.getUTCMonth() + 1;
        var year = dd.getUTCFullYear();
    }else{
        var day = dd.getDate();
        var month = dd.getMonth() + 1;
        var year = dd.getFullYear();
    }
    var year_month = year + "-" + month;
    var year_month_day = year + "-" + month + "-" + day;
    var quarters = [{ months: [1, 2, 3] }, { months: [4, 5, 6] }, { months: [7, 8, 9] }, { months: [10, 11, 12] }];
    var halfs = [{ months: [1, 2, 3, 4, 5, 6] }, { months: [7, 8, 9, 10, 11, 12] }];
    var quarter = 0;
    var half = 0;
    quarters.forEach(function(q, counter) {
        counter++;
        if (q.months.indexOf(month) != -1) {
            quarter = counter;
        }
    });
    halfs.forEach(function(h, counter) {
        counter++;
        if (h.months.indexOf(month) != -1) {
            // print(counter);
            half = counter;
        }
    });
    var stats = {
        "day": day,
        "month": month,
        "year": year,
        "quarter": quarter,
        "half": half
    }
    return stats;
}

db.personas.find({})
   .forEach(function(p){
       p.date = getDateStats(p.Date,'mmddyy','/', false);
       p.iso_date = new Date(p.Date);
       db.personas.save(p);
   });
   ```


4.	Para facilitar la tarea proporciono los datos ya ordenados en el fichero Output.json. Lo importamos desde el terminal de Windows.

< mongoimport –db test –collection personas < output.json

5.	Ahora ya temenos los datos ordenados en MongoDB y podemos lanzar una Query que nos muestre para cada día, la calle en la que ha habido más peatones entre las 10:00h y las 21:00h. Se proporciona la salida en el archivo “Respuesta.csv”. Si analizamos los datos, nos damos cuenta de que en 193 días del año, la zona en la que transitan más personas es SOUTHBANK. Por tanto, es esta la zona en la que por mayor flujo de personas, situaríamos nuestro negocio.  Para ver los datos de manera gráfica y ver que SOUTHBANK se corresponde con la zona más bulliciosa de negocios de Melbourne, he creado el siguiente mapa que podéis consultar pulsando en el enlace. 








# App
## Cómo inicializar
Run `npm install`

Para ejecutarlo en tu móvil (conectador por USB), ejecutar:
Run `ionic cordova run android`


Para ver si él móvil está conectado, ejecutar
Run `adb devices`

