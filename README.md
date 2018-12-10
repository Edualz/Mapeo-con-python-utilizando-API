# Mapeo con python utilizando API
In this work we made a program in Python where using a API we will be able to download data of diferent topics and translate them at the same time to make a base map, this program can work with any topographic map of the state.



# Introducción 

La API de Indicadores del INEGI permite consul-tar los datos y metadatos de los indicadores disponibles a nivel nacional, por entidad federa-tiva y municipio. Puede utilizar la API para crear aplicaciones que muestren la información direc-tamente de las bases de datos del INEGI en el preciso momento en que se actualiza.
Entonces lo que proponemos es realizar un programa que nos ayude a descargar algún dato del inegi para con la ayuda de esa infor-mación crear un mapa del tema en específico además se espera que este programa no sola-mente funcione con información de colima si no que funcione con cualquier información de cualquier parte de la república mexicana.

El sitio web hipertextual define una API como “un conjunto de funciones y procedimientos que cumplen una o muchas funciones con el fin de ser utilizadas por otro software” Es una sigla proveniente de las palabras en inglés Application Programming Interface, lo que se traduce en español como Interfaz de Programación de Aplicaciones.
Ahora bien, una API de Google Maps es un servicio de mapas de Google que brinda diferentes funcionalidades tales como: marcadores, asignación de rutas, trazar sectores dentro de un mapa, entre otras.  Entonces, ¿para qué sirve y qué puedes hacer con este gran servicio? ¡He aquí 4 útiles prácticas que permite!
1.	Crear una aplicación donde tengas que marcar una zona dentro del mapa o indicar instrucciones para llegar a un destino. Un ejemplo de apps que hacen uso de este servicio son Uber, WhatsApp, Tinder, Cabify, etc.  
2.	A través de una app web o móvil, gracias a la API de Google Maps puedes mostrar a los usuarios bares, cafeterías, aeropuertos o tiendas de alimentos cercanos, usando una lista filtrada con los lugares más relevantes para estos.
3.	Estimar la duración de un viaje en función de los datos históricos por horario y día de la semana.
4.	La API de Google Maps les permite a las aplicaciones aplicar un código de colores a las calles principales para reflejar el volumen actual del tráfico en tiempo real.
Entonces lo que proponemos es realizar un programa en Python que con la ayuda de una API de google permita crear un mapa del cualquier  tema en específico, además se espera que este programa no solamente funcione con información de colima si no que funcione con cualquier información de cualquier parte de la república mexicana.





# Desarrollo



Dentro de este documento se redactará el proceso que se estará llevando acabo para la elaboración del proyecto a realizar, el cual se realizara un tema de gran importancia, pues cabe decir que la programación se ha desarrollado a muy grandes rasgos la im-plementación de plasmar un mapa base a una imagen de Colima en donde podamos visualizar los diferentes cosas que se reali-zaran en el proyecto. Un ejemplo de este proyecto seria de que las empresas puedan realizar estudios de localización o de ver donde se encuentran sus demás dependen-cias por supuesto con datos reales que se encuentren a disposición de toda la pobla-ción que lo rodea. Un mapa es muy impor-tante ya que en el podemos encontrar todo lo que solicite la empresa para así nosotros realizarlo. 
Constituye el medio indispensable para la localización y la orientación que necesita-mos saber nosotros, además cumple con la función de incorporar información entendi-ble para el lector.
Este es otro claro ejemplo pero con Ja-vaScript:
La clase de JavaScript que representa un mapa es la Mapclase. Los objetos de esta clase definen un solo mapa en una pági-na. (Puede crear más de una instancia de esta clase; cada objeto definirá un mapa separado en la página). Creamos una nueva instancia de esta clase usando el newoperador de JavaScript.
Cuando crea una nueva instancia de mapa, especifica un <div> elemento HTML en la página como contenedor para el mapa. Los nodos HTML son hijos del documentobjeto JavaScript, y obtene-mos una referencia a este elemento a tra-vés del document.getElementById()método.
 
 En cada una de las áreas se encuentra una gran variedad de distintos temas de estudio que con el paso de los años y las tecnolo-gías INEGI las ha ido recolectando.
Para poder generar una API de INEGI es necesario colocar tu correo en el apartado generar token.
Nos mandara una clave que nos permitirá acceder a la información y generar el URL de la API
Este proyecto se quiso hacer con google maps pero a partir de junio del 2018 google empezó a cobrar por generar las APIS

Importamos librerías y con la función csv leemos nuestro archivo que contenga las claves asi podremos saber que clave le co-rresponde a cada estado.
Folium es la librería que nos permite crear mapas interactivos y gracias a esta librería podemos ubicar los puntos y verla de una manera clara y entendible sobre un mapa base.







# Manejo de datos



Lo que le implementamos a nuestro código es un menú que nos indicara de donde que-ríamos comenzar a mapear y en qué lugar queríamos terminar de mapear.
En el código anterior metíamos la dirección y el destino directo, pero ahora no. Pode-mos elegir cualquier estado con las siguien-tes claves.

Estados	Clave

Aguascalientes	2808

Baja California 	24093

Baja California Sur 	24368

Campeche 	17247

Chiapas	15309

Chihuahua 	19326

Coahuila 	20673

Colima 	26975

Durango 	19626

Edo. México 	2079

Guerrero 	1437

Hidalgo 	4577

Hidalgo 	4577

Jalisco 	27787

Michoacán 	26416

Morelos 	1441

Nayarit 	27016

Nuevo León	21725

Oaxaca 	14085

Puebla 	6735

Querétaro 	23076

Quintana Roo 	18086

San Luis Potosí 	28832

Sinaloa 	9393

Sonora 	44130

Tabasco 	12450

Tamaulipas 	23319

Tlaxcala 	23842

Veracruz 	8894

Yucatán 	18591

Zacatecas 	20361

El Api que utlizamos fue : 2afa231e-e8a3-4d06-a197-bc58962a07d0










# Codigo

#Importamos los modulos necesarios para realizar el trabajo 

import folium 

import json

import urllib2 

import pprint

#Definimos nuestras variables 


origen = "Colima"

destino = "Tijuana"

Key = "AIzaSyCazKtT-m8dQ9wcXnIlkRP8wKgXTeb-Js0"

#creamos nuestro url 


link = "https://maps.googleapis.com/maps/api/directions/json?origin=" + origen + "&destination=" + destino + "4&key=" + Key

#Prosesamos nuestro url para despues mostrar el json retornante 

response = urllib2.urlopen(link)

dat = json.loads(response.read())

pprint.pprint(dat)

datos = pd.read_csv('C:\\Users\\Eduardo\\Desktop\\Ingenieria en topogrfia FIC\\Tercer semestre\\Programacion de computadoras 

II\\ordinario programacion\\Claves.csv')


Est=datos['Estados']


clv=datos['Clave']


est=pd.Series.tolist(est)


clv=pd.Series.tolist(clv)


print(tabulate({'a':est,'b':clv}, headers=['Estados de México', 'Clave']))


test = json.dumps([s['geometry']['location'] for s in Js['array']], indent=3)


Coordinates = []

for i in range(len(dat['routes'][0]['legs'][0]['steps'])):
    lat = dat['routes'][0]['legs'][0]['steps'][i]['end_location']['lat']
    lon = dat['routes'][0]['legs'][0]['steps'][i]['end_location']['lng']
    u = [lon, lat]
    Coordinates.append(u)
    
 #imprimimos nuestras coordenadas
 
Coordinates

#creamos un GeoJson

Gj = {"type": "LineString", "coordinates": Coordinates}

p# Creamos el obejeto mapa con el modulo de folium 

Map = folium.Map(location=[22, -99],tiles = "Stamen terrain", zoom_start= 5)

folium.GeoJson(Gj).add_to(Map)

print (Gj)
#mostramos el mapa 


# Conclución


Como ya se mencionó antes este programa en un inicio solo hacía la ruta del origen y del destino que se le agregara al código ahora lo que hace el programa es que desde la ter-minal podemos escoger el origen y el des-tino y asi poder plasmarlo en un mapa. Además que anterior mente lo hacíamos con una API de Google maps pero ahora lo hicimos un la API de iNEGI

Este trabajo en un comienzo se procuro mapear con la ayuda de la API de INEGI pero al momento de querer generar la API teniamos que llenar un pequeño forulario para que el INEGI nos mandara una clave al correo para poder generar la API, pero se hicieron varios intentos pero nunca nos mandaron la clave, asi que decidimos hacer el proagrama con una API de Google, una de las cosas con las nos topamos es que en junio del 2018 Google comenzo a cobrar por generar las API pero entre los compañeros buscamos y alguien nos proporciono una que ya tenia, por lo que usamos esa en el programa.




