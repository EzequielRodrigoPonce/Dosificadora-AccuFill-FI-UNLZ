<p align="center" width="100%">
    <img width="15%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Readme.md/321138189_722314939154857_3310166726490044259_n.jpg" align="left">
    <img width="15%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Readme.md/378230559_797453282383428_4968693939392363229_n.jpg" align="right">
</p>
<br><br><br>


                
<h1 align="center">Dosificadora Peristáltica</h1>
<br>
<br>
<h2 align="center">Integrantes:</h2>
<h3 align="center">Ponce, Rodrigo Ezequiel</h3>
<h3 align="center">Obermann, Cristian</h3>


<br><br><br>

Este proyecto se propone brindar una alternativa más barata, personalizable e intuitiva a la dosificación de líquidos para la industria alimenticia. En el mercado, este tipo de máquinas se pueden obtener una gran variedad de precios, caudales y precisión, pero su valor es muy alto en contraste con los componentes que forman el equipo, que pueden ser adquiridos por un precio relativamente bajo. Este proyecto además tiene como objetivo facilitar el uso mediante una interfaz de usuario amigable que se controle desde un Smartphone o una computadora, generalmente las dosificadoras con este tipo de funciones son de las más costosas de su tipo.

## Descripción:

El proyecto consiste en desarrollar una solución económica y funcional para la dosificación de dos fluidos denominados componente “A” y componente “B” para obtener una preparación o distintas formulaciones que la industria alimenticia considere necesarias a partir de dos componentes.
Se construirá un cubículo donde se concentran todos los componentes electrónicos y el espacio de dosificación que funcionará con un motor eléctrico y diversos sensores que harán al automatismo y control del proceso. Asimismo, se construirán dos bombas peristálticas encargadas de la dosificación.
Se tendrá un espacio donde colocar un recipiente para ser leído por un sensor que permite que se aplique la cantidad programada de un determinado fluido “A” Y “B”, luego se tendrá la formulación deseada. 
Este prototipo está destinado a ser construido como modelo de prueba para la industria alimenticia, con un nivel de precisión y tolerancia acorde a dicha industria y etapa del proyecto.

## Especificación de Requerimientos de la Dosificadora

El usuario podrá especificar la cantidad de líquido y las proporciones del líquido A y B que se dosificarán mediante un servidor web, través de un Smartphone o computadora, siguiendo una dirección de internet ó escaneando un código QR, se podrá controlar con una interfaz intuitiva.

Una vez especificadas las proporciones a dosificador, se deberá transportar un recipiente vacío sobre una plataforma que se encuentra dentro del equipo, en el punto donde se deposita el recipiente está tendrá un sensor óptico capaz de detectar su presencia, esto hará que la plataforma traslade el recipiente y se detenga debajo de la manguera a la salida de la bomba peristáltica.
Los dos recipientes que contienen los líquidos A y B estarán encima de balanzas de precisión. Estas ayudaran a mejorar la precisión con la que se distribuyen los líquidos.
Primero se dosifica la cantidad de líquido A según lo especificado por el usuario y luego el sistema, mediante la balanza, calcula la cantidad de líquido A que se distribuyó y con esos valores determina la cantidad de líquido B que se proporcionará a continuación.  
Las bombas peristálticas serán capaces de distribuir líquido dentro de un rango de caudal de 100 a 1500 mL/min.    

## Proceso de Peristálsis:
Las [bombas peristálticas](https://en.wikipedia.org/wiki/Peristaltic_pump "Wikipedia") funcionan cuando los rodillos comprimen la manguera al girar, creando un vacío que succiona fluido a través de esta. En este tipo de bomba, solo la manguera de elastómero flexible entra en contacto con el fluido, eliminando el riesgo de que la bomba contamine el fluido o a la inversa.
En la Imagen se puede observar el fluido entrando en la manguera de la bomba, atrapado por el rodillo del cabezal de bombeo, y expulsado cuando el próximo rodillo pasa sobre la manguera. Al girar los rodillos, se forma un vacío en la manguera, succionando más fluido, para el próximo paso del rodillo.
El cierre total de la manguera al ser comprimida entre el rodillo y la pista (oclusión) proporciona a la bomba una acción de desplazamiento positivo, evitando el reflujo y eliminando la necesidad de válvulas reguladoras cuando la bomba no está en funcionamiento.


<p align="center" width="100%">
    <img width="45%" src="https://i.makeagif.com/media/1-27-2016/YvQtiC.gif">
</p>

<br>

## Materiales Necesarios: 

| Componente | Cantidad | Precio [US$] |
|---|:---:|:---:|
| ESP32 | x2 | 22
| MOTOR NEMA 17 |        x2| 60.5
| DRIVER DRV8825 |        x2| 6.6
| CELDA DE CARGA HX711 |            x2| 14
| PLACA EXPERIMENTAL      |             x1| 3.15 
| PACK DE CABLES |              x1| 3.83
| RODAMIENTOS 684Zz |              x12| 8.5
| TUBO GRADO ALIMENTICIO |              x2| 6.8
| SENSOR ULTRASONICO |      x1| 1.64
| SENSOR INFRARROJO|           x2| 6.58
| FILAMENTO PLA|           x1| 8.22
| TORN. + ARANDELAS M4|           x12| 1
| EXTRAS (CABLES, TRAFOS, ESTAÑO, ETC.)|           x1| 13.7
| DISPLAY LCD 20X4|           x1| 7.8
| FUENTE DE ALIMENTACIóN 12V|           x1| 11
| TOTAL|           | US$ 175.32

 
<br>

## Circuito Electronico:  

En la electrónica se investigaron y se utilizaron los siguientes componentes:<br>
<br>**NEMA 17 y DRV8825**: Motor PaP y su controlador utilizado en la bomba para dosificar líquidos.
<br>**MOTOR DC**: Utilizado para girar la plataforma que rotará el recipiente debajo del pico dosificador
<br>**SENSOR IR**: Utilizado para detectar la presencia del recipiente vacío en la plataforma y debajo del pico dosificador.
<br>**MICRO SWITCH**: Utilizado en la puerta de la dosificadora para interrumpir todos los procesos en caso de que esta se abra.
<br>**CELDA DE CARGA Y HX711**: Utilizada para pesar constantemente la cantidad de líquido en los tanques contenedores.
<br>**DISPLAY LCD**: Utilizado para mostrar la dirección web de la dosificadora y las cantidades a dosificar.
<br>**ESP32**: Se utilizaron dos, uno que contiene las celdas de carga y el LCD, y otra que contiene todo lo demás, se dividieron en dos ESP32 por las incompatibilidades que existen entre las celdas de carga y los NEMA 17 si se usan al mismo tiempo. Para soluciones estos problemas de compatibilidad se consultó al profesor de Fundamentos de los Computadores Digitales de la UNLZ.
<br>**FUENTE DE COMPUTADORA**: Se utilizó para alimentar toda la dosificadora. Se consultó al profesor de Electrónica la UNLZ, la forma de calcular el voltaje y amperaje necesario de la fuente a utilizar. 


<br>
<p align="center" width="100%">
    <img width="95%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Circuito%20de%20Dosificadora/Circuito%20de%20ESP%20con%20Motores.png">
</p>
<br>


<br>
<p align="center" width="100%">
    <img width="95%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Circuito%20de%20Dosificadora/Circuito%20de%20ESP32%20Con%20Pag%20Web.png">
</p>
<br>



<br>
<p align="center" width="100%">
    <img width="73%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Readme.md/GIF%20Parte%201.gif">
</p>
<br>
<br>
<br>

<p align="center" width="100%">
    <img width="73%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Readme.md/GIF%20Parte%202.gif">
</p>

<br>
<br>
<br>
<p align="center" width="100%">
    <img width="73%" src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Readme.md/GIF%20Parte%203_1.gif">
</p>
<br>
<br>
<br>


<table align="center" style="margin-left: auto; margin-right: auto;">
<tr>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Ensamblando%20bomba.jpg" width="300"> <br>Ensamblaje de Bomba </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Probando%20bomba%20con%20el%20primer%20motor%20CC.jpg" width="300"> <br>Testeo </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Revisi%C3%B3n%20de%20pines.jpg" width="300"> <br>Cableado de Circuito </td>
</tr>
<tr>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Imagen%20de%20WhatsApp%202023-12-01%20a%20las%2023.33.35_a418374a.jpg" width="300"> <br>Calibración </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Preparativos%20para%20la%20estructura.jpg" width="300"> <br>Lijado de Dosificadora </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Pintando%20la%20estructura%20del%20prototipo.jpg" width="300"> <br>Pintado de Dosificadora </td>
</tr>
<tr>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/distribuci%C3%B3n%20y%20montaje%20de%20cables%20en%20la%20base.jpg" width="300"> <br>Armado Final </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/colocaci%C3%B3n%20de%20luces%20en%20cabina%20de%20dosificaci%C3%B3n%20y%20bombas.jpg" width="300"> <br>Vista Frontal  </td>
<td><img src="https://raw.githubusercontent.com/EzequielRodrigoPonce/Dosificadora-AccuFill-FI-UNLZ/main/Imagenes/Probando%20comunicaci%C3%B3n%20serial%20entre%20pagina%20y%20motores.jpg" width="300"> <br>¡Dosificadora Completada! </td>
</tr>
</table>
<br>
<br>
<br>



## Posibles Etapas Futuras a Desarrollar:

Una etapa posible sería encontrar una forma de poder comparar los datos recibidos de la balanza y la cantidad de pasos del nema 17 al dosificar para aumentar la precisión del líquido dispensado. 
Para poder obtener valores confiables que relacionen la cantidad de pasos del nema 17 con la cantidad de líquido dosificado es necesario modificar el diseño de la bomba peristáltica, porque la manguera tiene demasiado juego entre la carcasa impresa y el rodamiento que la aprieta, debido a esto no se logra formar un vacío que impida que cuando se detengan los motores los líquidos retrocedan de vuelta al recipiente expendedor.
Otra etapa sería aumentar la velocidad de dosificación de la bomba manteniendo la estabilidad del dispositivo o agregar más bombas a la dosificadora para permitir múltiples dosificaciones independientes entre sí, esto hará que el proyecto sea más rentable y útil en aplicaciones de la industria.
En el siguiente video se muestra una dosificadora multi-canal:


<p align="center" width="100%">
  <a href="https://www.youtube.com/watch?v=ZArngSEx4A0" title="Dosificadora Multi Canal">
    <img src="http://i3.ytimg.com/vi/ZArngSEx4A0/hqdefault.jpg" alt="Dosificadora Multi Canal" class="left">
  </a>
    <img width="49%" src="https://m-tech.com.au/wp-content/uploads/ezgif.com-optimize.gif" align="right">
</p>

