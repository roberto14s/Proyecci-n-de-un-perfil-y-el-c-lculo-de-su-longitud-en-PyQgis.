
![](https://portal.ucol.mx/content/micrositios/188/image/Escudo2021/1_Linea/UdeC%20Abajo_Negro.png)
# Proyección de un perfil y el cálculo de su longitud en PyQgis
*Projecting a profile and calculating its length in PyQgis*

Facultad de Ingeniería Civi

**3°B**

Profesor: Sebastián González Zepeda

**Roberto Alejandro Navarro Obispo** (1) Colima - Coquimatlán Kilómetro 9, Jardines del Llano, 28400 Coquimatlán, Col., 20186496, <rnavarro@ucol.mx>


## **Resumen Ejecutivo**
En este documento se presentarán las bases para la comprensión de un código el cual trabaja mediante la aplicación de la consola de Python en el software de Qgis, hace que muestre la capa ráster del estado de Colima, de igual forma muestra el perfil con el que se trabajaron los datos, y de éste calcula la longitud.

## **Abstract**
This document will present the bases for the understanding of a code which works through the application of the Python console in the Qgis software, makes it show the raster layer of the state of Colima, in the same way it shows the profile with which The data was worked on, and from this the length was calculated.

## **1.Introducción.** 
La nivelación de perfil tiene como objetivo determinar las cotas o elevaciones de puntos con distancias conocidas sobre un trazo para obtener el perfil del trazo.  

Cuando se requiere del estudio de una vía de comunicación terrestre ya sea de camino, introducción de agua potable, un sistema de alcantarillado, un canal, entre otros; se utiliza este procedimiento el cual se encarga de determinar las elevaciones, cotas y alturas o intervalos cortos sobre una línea fija generalmente sobre el centro de un eje de la vía que se presenta alojar.  

Por lo general esos intervalos son en forma longitudinal a cada 20m y cambio de pendientes importantes a estos intervalos se les llama estaciones complejas o estaciones cerradas a los oros puntos se les conoce como estaciones intermedias, en cada estación se clava una estaca a la cual tiene su respectivo kilometraje.  

Programar significa tener la habilidad de crear y codificar un algoritmo para que pueda ser ejecutado por una computadora. Es decir, se desarrollan un conjunto de instrucciones que le indican a la computadora cómo hacer ciertas tareas. En la actualidad, la programación es catalogada como un lenguaje tecnológico fundamental. ¿Por qué es tan importante aprender programación hoy en día? el constante progreso de la tecnología aplicado a cualquier ámbito profesional, el desarrollo de capacidades resolutivas, la amplia oferta de trabajo que ofrece la industria IT.

Un perfil topográfico es un corte o sección a lo largo de una línea dibujada en un mapa. En otras palabras, es como si se pudiera rebanar una porción de la Tierra y separarla del resto para poder verla de lado a lado; la superficie de esta rebanada sería el perfil topográfico. ¿Cuál es el uso de un perfil topográfico? Un perfil topográfico permite un mejor conocimiento de los Modelos Digitales de Elevaciones (MDE), ya que el análisis de elementos lineales es más sencillo que el análisis de superficies.

## **2.Desarrollo**

**Hablemos de Historia**

Hace cuatro mil años, los conceptos de matemáticas eran básicos, sin embargo, los egipcios fueron capaces de lograr maravillas. Utilizaron los predecesores de los instrumentos topográficos modernos para realizar muchas hazañas, desde canales hasta pirámides. Un equipo de topógrafos del antiguo Egipto utilizaba cuerdas de medición, plomadas, instrumentos de observación e instrumentos de nivelación. 

Los primeros registros históricos del uso de la topografía datan del año 1400 antes de Cristo cuando el faraón egipcio Sesostris, ordenó la delimitación de terrenos para la recaudación de impuestos y las inundaciones del río Nilo arrastraron unos linderos de estas. (Flores, 2022) En el antiguo Egipto fue necesario emplear el uso de la topografía con el fin de recaudar impuestos, cómo es bien sabido para que una sociedad funcione correctamente es necesario recaudar impuestos de sus ciudadanos con el fin de proveer o de satisfacer las necesidades de estos, otro uso que se le dio a la topografía en el antiguo Egipto fue de delimitar los terrenos de sus ciudadanos lo cual en tiempos modernos se le puede llamar como el levantamiento topográfico.

Los antiguos topógrafos desarrollan una serie de actividades cómo hoy en día las hacemos, estos topógrafos se le designaron el nombre de los “estiras cuerdas” quienes utilizaron cuerdas con patrones determinados cada cierta distancia para medir y redefinir los límites estas cuerdas corresponden a unidades de longitud convencionales, como el denominado “codo”. bueno cada nudo estaba separado en la cuerda por equivalencia de 5 codos, por la inexactitud que esta media representada se estableció que hacia el año 3000 antes de Cristo el codo real como patrón de medida convencional, tal vez basado en la medida del codo de algún faraón cuya dimensión era de 52.3cm. (Flores, 2022) cuando los topógrafos antiguos realizaban un levantamiento topográfico de un terreno no era exacto ya que variaba la longitud del codo por eso se estableció y la medida de cada nudo debe de estar separado a 52.3 cm con el único fin de mantener una precisión y una exactitud de medida a lo cual esto facilita realizar dicho levantamiento.

Principales personajes y sus aportaciones hacia la topografía. 

Thales de Mileto: fue un filósofo, astrónomo y matemático griego nació en Mileto en el año 624 a. de C. de acuerdo con el pensador griego Apolodoro, y murió a la edad de 78 años durante la quincuagésima octava olimpíada (548-545 a. de C) Tales es el padre tradicional de la matemática griega. Tales era un hombre esencialmente práctico comerciante, hábil en ingeniería, astrónomo, filósofo, estadista, geómetra. Como lo que ahora llamaríamos ingeniero, estuvo dirigiendo obras hidráulicas y se dice que desvió el curso del río Halis mediante la construcción de diques. (Gómez, 22) 
Como sabemos las aportaciones de este personaje son demasiadas y una gran parte de su conocimiento fue llevado al área matemática para lo cual hoy en día es usada por ejemplo el teorema de Thales de Mileto el cual establece lo siguiente.

![image](https://user-images.githubusercontent.com/119511302/206811628-702bd385-a99b-498b-8aa6-91c2034a5f3e.png)

Figura #0. Thales de Mileto fuente: Google.

“Si dos rectas r y r’ se cortan por un sistema de paralelas, los segmentos determinados por los puntos de intersección sobre una de ellas son proporcionales a los determinados por los puntos correspondientes en la otra”. Thales de Mileto. 

En la materia de topografía se hace el constante uso de la geometría la cual es una rama de las matemáticas que se dedica al estudio de las figuras en un plano o espacio. Así, analiza sus características y medidas como el perímetro, área y volumen. Esta disciplina se encarga de estudiar, por ejemplo, los polígonos (que son figuras bidimensionales constituidas por varios segmentos consecutivos no colineales, formando un espacio cerrado) (Westreicher, 2022) los cuales constantemente en esta área son usados para determinar una superficie de un lote donde se levantará topográficamente.

Como sabemos la geometría es una ciencia con muchas aplicaciones y sirve de base para otros campos de estudio como la física, la geografía, la arquitectura y la topografía (estudio de la superficie terrestre). Por ejemplo, nos sirve para calcular las medidas de determinados espacios o construcciones. (Westreicher, 2022) como ingenieros estamos constantemente involucrados en saber cómo funciona el levantamiento topográfico de un predio ya que tenemos que tomar en cuenta la forma geométrica del polígono para saber qué tipo de método para determinar las distancias se usarán las cuales en este proyecto usaremos los métodos de ligas, radiaciones y el de diagonales cada uno de estos tiene su uso correspondiente.

**¿Matemáticas en topografía?**

La topografía se basa, en primer lugar, en algunas ramas de la matemática, tales la trigonometría y la geometría. Un levantamiento topográfico constituye un conjunto de operaciones que tiene como objetivo conocer la posición relativa de los puntos sobre la tierra en base a su longitud latitud y elevación (x,y,z). Para este estudio operacional, la topografía se dividió en altimetría, planimetría. Trigonometría. 

La trigonometría en un principio fue el arte de calcular la información perdida mediante simple cálculo. Dada la suficiente información para definir un triángulo, permite calcular el resto de las dimensiones y de ángulos. La topografía es el estudio de los métodos que tiene por objeto la representación gráfica de la superficie de la Tierra, con sus formas y detalles, tanto naturales como artificiales. En ella la trigonometría es el pan de cada día, ya que para tomar mediciones con la estación total es necesaria para hacer «levantamiento de un terreno» y representarlo gráficamente en un plano con una escala determinada. 

La trigonometría es una base fundamental ya que sin ella sería imposible conocer distancias, coordenadas, medidas angulares, etc. El sistema de representación adoptado por la topografía muestra los diferentes puntos del espacio tomando un plano comparación, sustituyendo la figura en el espacio de tres dimensiones (x, y, z) por un plano de tan solo dos (x, y). Pero para que el sistema sea reversible se precisa añadir sobre esta representación un tercer elemento z o altura del punto sobre el plano de comparación (cota). Geometría. 

La geometría es la base de la topografía ya que se toman distancias horizontales y ángulos para determinar tanto la ubicación horizontal de un objeto como la elevación con respecto a una horizontal imaginaria del mismo objeto.

**Planteamiento del problema**

Una problemática que se presentará al realizar el levantamiento topográfico es el error de nivelación debido al tomar las mediciones de manera incorrecta; recordando la teoría de los errores, dictamina lo siguiente: 

1. Ninguna medida es exacta. 

2. Toda medida contiene errores. 

3. Nunca se conocerá el valor verdadero de una dimensión. 

4. El error exacto que hay en una medida siempre será desconocido. Las equivocaciones se detectan mediante la comprobación sistemática de todo trabajo y se eliminan haciendo parte de este o bien todo de él. 

En toda medición aparecen tres tipos de errores: 

a) Errores naturales. 

b) Errores instrumentales. 

c) Errores personales. 

Tipos de errores Los errores que contienen las medidas son de dos tipos: 

1) Errores sistemáticos. 

2) Errores accidentales. 

Los errores sistemáticos, se comportan de acuerdo con leyes físicas susceptibles de ser modelados matemáticamente, por lo que su magnitud puede calcularse y su efecto eliminarse. 

Los errores accidentales son los que quedan después de haberse eliminado las equivocaciones y los errores sistemáticos. Son ocasionados por factores que quedan fuera del control del observador, obedecen a las leyes de la probabilidad y se conocen también con el nombre de errores aleatorios. 
Cuando se detecta una equivocación, generalmente es mejor repetir la medición. Sin embargo, si se dispone de un número suficiente de medidas de la cantidad que sí están de acuerdo entre sí, puede descartarse el valor que sea divergente del resultado. Debe considerarse el efecto que ocasionaría el valor antes de descartarlo.



**Nivelación de perfil**

![](http://4.bp.blogspot.com/_oKSDCrhgRhk/TE9KOhus3NI/AAAAAAAAADY/kanzAg_9XkY/s1600/nivel_-_desnivel.jpg)

Figura #1. Gráfico de una nivelación de perfil. Fuente: Google

Es la operación, usualmente por nivelación directa, de determinar las elevaciones de puntos a cortos intervalos a lo largo de una línea localizada tal como el centro para una carretera o tubería. Es también usada para determinar elevaciones de cortes o secciones, contornos y gradientes.

Son colocadas estacas a intervalos regulares sobre esta línea, usualmente la línea central. El intervalo escogido es uno conveniente de acuerdo con la longitud del perfil, tal como 100, 50, 25 mts. Los puntos al intervalo escogido, tal como por ejemplo 100 m son llamados estación completa y todos los otros puntos, estaciones “más”, (+). Por ej. Una estaca colocada a 1600 m del punto de inicio es numerada “16+00” y una colocada a 1,625,” 16+25, cuando se usa intervalos de 100 m. En caso de usar intervalo de 1000 m la numeración sería	1+600 y 1+625, correspondientemente. Las elevaciones por medio de las cuales el perfil se construyen son levantadas tomando lectura de nivelación sobre las estacas o en puntos intermedios donde ocurren cambios de pendientes.

![](https://drive.google.com/uc?export=view&id=1WQJfl6Io_q4l9vtbIM_3lDi9A9UG7cr0)

Debe tenerse cuidado en la escogencia de los puntos de cambio ya que éstos son los puntos de enlace o de transferencia de cotas. Deben ser puntos firmes en el terreno, o sobre estacas de madera, vigas de puentes, etc.

Siendo los puntos de cambio puntos de transferencia de cotas, en ellos siempre será necesario tomar una lectura adelante desde una estación y una lectura atrás desde la estación siguiente.

Procedimiento:

- Se colocan desde el principio de la línea, una serie de puntos llamados estaciones completas, los cuales van a estar una de la otra a una distancia de 20m (por lo general, ya que puede ser otra 10m, 50m etc.), aunque esta distancia puede variar, además de las estaciones completas, también se ubican los puntos donde hay cambios de dirección, cambios de pendiente, etc. llamados subestaciones.

- Estación Completa: son los puntos situados cada 20 metros completos, ejemplo: 0+020, 0+100, 0+240, 0+980, 1+000, 1+120, etc.
- Subestación: son puntos situados en la línea central que no están a 20 metros completos, ejemplo: 0+95.40, 0+985.40, 1+125.30, 1+242.6, etc.



Las elevaciones con que se construyen los perfiles se obtienen de las lecturas del estadal tomadas en cada estación y subestación.

Ejemplo de registro:

![](https://drive.google.com/uc?export=view&id=1-JmtzWf3QFOnUFx-aOV5DmBl_cmcfU7v) 

Figura #2. Ejemplo de registro de una nivelación de perfil. Fuente: M.C. Rosendo Sánchez

## **2.1. Metodología** 
#
Comprobación ida y vuelta

Esta comprobación se realiza repitiendo la nivelación en sentido contrario, ya sea siguiendo la misma ruta u otra distinta. Este procedimiento tiene la ventaja de que, al repetir la nivelación en dirección contraria, se pueden eliminar ciertos errores de acumulación

Procedimiento:

Es igual a la simple con la única diferencia que el aparato se plantara más de una vez y por consiguiente la altura de instrumento será diferente cada vez que se cambie. Este tipo de nivelación se realiza cuando los terrenos son bastantes accidentados y exceden visuales de 200 m., en otras palabras, la nivelación compuesta es una serie de nivelaciones simples amarradas entre sí por puntos de cambio o de liga del aparato.  

|**P.V.**|**+**|**A.I.**|**-**|**COTA**|
| - | - | - | - | - |
|**BN1**|0.274|355.254| |354.98|
|**0+000**|0.595|353.88|1.969|353.285|
|**0+020**| | |2.683|351.197|
|**0+040**| | |3.88|350|
|**0+053**| | |4.415|349.465|
|**PL1**|1.015|351.187|3.708|350.172|
|**0+060**| | |1.588|349.599|
|**0+080**| | |1.105|350.082|
|**0+100**| | |0.648|350.539|
|**0+120**| | |0.161|351.026|
|**PL2**|2.888|353.986|0.089|351.098|
|**0+140**| | |2.425|351.561|
|**0+156**| | |1.945|352.041|
|**0+160**| | |1.514|352.472|
|**0+180**| | |1.023|352.963|
|**PL3**|3.816|357.64|0.162|353.824|
|**0+200**| | |3.214|354.426|
|**0+220**| | |0.625|357.015|
|**PL4**|3.772|360.787|0.625|357.015|
|**0+240**| | |3.003|357.784|
|**0+260**| | |2.257|358.53|
|**0+269**| | |1.914|358.873|
|**0+280**| | |1.687|359.1|
|**0+300**| | |1.347|359.44|
|**0+320**| | |1.038|359.749|
|**0+340**| | |0.709|360.078|
|**0+349**| | |0.602|360.185|
|**BN2**| | |0.383|360.404|
|**Comprobación de Vuelta**|
|**BN2**|0.349|360.753| |360.404|
|**PL4**|0.118|357.132|3.739|357.014|
|**PL3**|0.231|354.053|3.31|353.822|
|**PL2**|0.01|351.108|2.955|351.098|
|**PL1**|3.485|353.646|0.947|350.161|
|**PL0**|2.229|355.506|0.369|353.277|
|**BN1**| | |0.532|354.974|

Comprobación Ida y Vuelta: se efectúa la nivelación en un sentido (nivelación de ida), trabajando con el método del punto medio, concluida esta, se inicia la nivelación de regreso, pudiendo utilizar los mismos PL’s que se usaron en el primer recorrido.

![](https://drive.google.com/uc?export=view&id=14MH49QmR_xI0EOpw1nF_wTxpEqIQ4aNw)

EL trabajo de campo se realizó en el campus Coquimatlán de la Universidad de Colima, se necesitó de importantes instrumentos topográficos, así como la adecuada indumentaria para su realización. Se dio principio con el reconocimiento del terreno del cual se tenía que obtener el perfil, consecutivamente en la parte sur del campus en donde se encuentra un estacionamiento, se indicó un banco de nivel (BN) teniendo una cota arbitraria.


**Qgis**

QGIS es un Sistema de Información Geográfica (SIG) de Código Abierto licenciado bajo GNU - General Public License . QGIS es un proyecto oficial de Open Source Geospatial Foundation (OSGeo). Corre sobre Linux, Unix, Mac OSX, Windows y Android y soporta numerosos formatos y funcionalidades de datos vector, datos ráster y bases de datos.

QGIS funciona en diferentes sistemas operativos: Linux, Windows, Mac y Android. Además, se puede instalar en una llave USB, lo que permite transportar QGIS de un ordenador a otro sin tener que instalarlo.

Uno de sus puntos fuertes es la interoperabilidad y te permitirte trabajar con una multitud de datos vectoriales y raster. Por citar algunos:

- Formato Shapefile (.shp formato nativo de QGIS) desarrollado por ESRI ArcGIS.
- Formatos MapInfo (.tab, mif-mid).
- Formato KML de Google Earth.
- Formatos DAO (Autocad DXF).

![QGIS](https://geomatiqueagricole.ca/wp-content/uploads/2019/01/QGIS_logo_2017.svg_-1024x305.png)
Figura #4. Logo de Qgis.

**Python**

Python es un lenguaje de programación orientado a objetos de alto nivel y fácil de interpretar con sintaxis fácil de leer. Ideal para prototipos y tareas ad hoc, Python tiene un amplio uso en computación científica, desarrollo web y automatización. Como lenguaje de programación para principiantes y de uso general, Python es compatible con muchos de los principales científicos de computadoras y desarrolladores de aplicaciones en todo el mundo.


![Python Programación - 14102 - Otras clases o cursos - Ciudad Autónoma ...](https://download.logo.wine/logo/Python_(programming_language)/Python_(programming_language)-Logo.wine.png)
Figura #5. Logo de Python.

## **3.Manejo de datos**

Para este programa se realiza un análisis de las diferentes librerías de PyQgis, la cual es una consola de Python en el software de Qgis. Primeramente se analiza la capa del vector, la cual fue resultado de los datos de una práctica de campo llevada a cabo en la Facultad de Ingeniería Civil en el camino del estacionamiento. Una vez obtenido el shapefile del vector, se realiza un programa el cual permite abrir una capa de archivo “.shp” y de esta misma calcula la longitud que esta tiene.



![Interfaz de usuario gráfica, Texto, Aplicación

Descripción generada automáticamente](Aspose.Words.07d8cf39-75e0-4b01-a6c3-d2db387911cc.014.png)



![Interfaz de usuario gráfica, Texto, Aplicación, Chat o mensaje de texto

Descripción generada automáticamente](Aspose.Words.07d8cf39-75e0-4b01-a6c3-d2db387911cc.015.png)





## **4.Resultados**

from PyQt5.QtCore import \*

from PyQt5.QtGui import \*

from qgis.core import \*

from qgis.gui import \*

from osgeo import gdal, osr

from PyQt5.QtCore import QVariant

#Vector

perfil = 'C:\\PyQGIS\\Perfil.shp'

perfil = QgsVectorLayer(perfil,'perfil','ogr')

#Raster

colima ='C:\\PyQGIS\\B5.TIF'

fileInfo = QFileInfo(colima)

baseName = fileInfo.baseName()

raster = QgsRasterLayer(colima, baseName)

QgsProject.instance().addMapLayer(raster)

QgsProject.instance().addMapLayer(perfil)

layer = qgis.utils.iface.activeLayer()

features = layer.selectedFeatures()

for f in features:

`    `geom = f.geometry()

`    `print("Length:", geom.length())



for field in perfil.fields():

`    `print(field.name(), field.typeName())

## **5.Conclusion**

En relación a todo lo visto durante todo el semestre, se realizó un proyecto en el cual nos basamos en pyqgis, la cual es la librería de QGIS para ejecutar código Python. Se realizo un codigo con el lenguaje de programacion ya mencionado, en el cual a partir de un vector ya creado de un perfil se añade a una imagen raster de Colima. Conforme con esta libreria,observamos que tiene bastante relación dentro de nuestra carrera, pues la aplicación de los diferentes códigos vistos en clases, nos facilitan y agilizan la interacción con la plataforma Qgis, así bien consideramos que la aplicación de estos códigos y similares en la rama de geomatica y topografica es importante su conocimiento y aplicacion para futuros proyectos academicos como personales.

Concluimos que el uso de la tecnología para la realización de cálculos es importante, ya que estos se realizan de una manera rápida y eficaz, pudiendo así menorar el tiempo en la verificación de la nivelación. La nivelación es una operación fundamental para el ingeniero, tanto para poder confeccionar un proyecto, como para lograr replantear el mismo. Las aplicaciones más comunes de la nivelación son: En proyecto de carreteras y canales que deben tener pendientes determinadas. Situar obras de construcción de acuerdo con elevaciones planeadas. Calcular volúmenes de terracería. (Volúmenes de tierra). Investigar características de drenaje y escurrimiento de superficies. Establecer puntos de control mediante el corrimiento de una cota.

Recordemos que la nivelación geométrica o nivelación diferencial es el procedimiento topográfico que nos permite determinar el desnivel entre dos puntos mediante el uso del nivel y la mira vertical. La nivelación geométrica mide la diferencia de nivel entre dos puntos a partir de la visual horizontal lanzada desde el nivel hacia las miras colocadas en dichos puntos. Cuando los puntos a nivelar están dentro de los límites del campo topográfico altimétrico y el desnivel entre dichos puntos se puede estimar con una sola estación, la nivelación recibe el nombre de nivelación geométrica simple. Cuando los puntos están separados a una distancia mayor que el límite del campo topográfico, o que el alcance de la visual, es necesario la colocación de estaciones intermedias y se dice que es una nivelación compuesta.

## **6. Referencias**

• Gamez W. (2013). Texto Básico Auto informativo de topografía general. Universidad Nacional Agraria.

• García Márquez, Fernando. (1994). Curso Básico de Topografía. Árbol Editorial, S.A. de C.V. México, D.F

• Reales, H. (2019). Introducción a la altimetría. Facultad de Ingenierias de la Universidad Tecnológica de Chocó.

• Zamarripa, M. (2010). Apuntes de Topografía. Facultad de Estudios Superiores Acatlán

• breco. (31 de 10 de 2022). abreco.com.mx.Obtenido de abreco.com.mx: https://www.abreco.com.mx/glosario_topografia.htm#:~:text=TRANSITO%3A,con%20solo%20tres%20tornillos%20nivelantes.

• CAMPOS, A. O. (31 de 10 de 2022). prezi.com. Obtenido de prezi.com: https://prezi.com/jri9j2z0l1wi/mate-aplicada-atopografia/#:~:text=La%20topograf%C3%ADa%20se%20basa%2C%20en,x%2Cy%2Cz).

• Eduard., L. (31 de 10 de 2022). acolita.com. Obtenido de acolita.com: https://acolita.com/evolucion-de-lastecnicas-topograficas/

• qgis. (31 de 10 de 2022). qgis.org. Obtenido de qgis.org: https://www.qgis.org/es/site/about/index.html

• rmsgeoespacial. (31 de 10 de 2022). rmsgeoespacial.com. Obtenido de rmsgeoespacial.com:https://rmsgeoespacial.com/comoseutilizaungpstopografico/#:~:text=Un%20gps%20topogr%C3%A1fico%20nos%20ayuda,al%20sistema%20de%20posicionamiento%20satelital
