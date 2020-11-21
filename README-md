# OSC e interacción audio-video

En esta sesión revisaremos algunos tópicos relacionados con la comunicación OSC y las posibilidades de la interacción audiovisual.

Anteriormente hemos mencionado que hay dos formas de realizar esto, utilizando un programa como motor gráfico y otro como motor de audio o utilizando el mismo programa para ambas cosas.

Supercollider cuenta con un motor gráfico, sin embargo, es bastante deficiente si lo comparamos con las posibilidades de Processing.

Entonces, utilizaremos SuperCollider y Processing para realizar un pequeño ejercicio de interacción por medio de OSC.

Antes de eso, realizaremos un pequeño ejercicio de OSC para entender cómo funciona este protocolo.

## Redes

OSC parte del paradigma de las redes y de las computadoras interconectadas. Si bien podemos pensar en red cuando utilizamos nuestra computadora para conectarnos a internet también podemos pensar en otro tipo de conexiones que no necesariamente nos dan acceso a la red pero que sí nos permiten realizar intercambios entre computadoras conectadas dentro de una misma red. 

Antes de conectarnos a la red para acceder, por ejemplo, a la página de [OpenSoundControl](http://opensoundcontrol.org) es necesario conectarnos a una red que primero es local. 

Esta red puede ser la de nuestra casa o la de centro. Esta primer conexión permite gestionar quién tiene acceso y quién no. Pero también puede servir para intercambiar información en una red local. 

Entonces, es posible conectarnos a un router que después puede darnos conexión a la red pero que también nos permite intercambiar información entre computadoras sin que haya acceso a la web global. 

Cabe destacar que podemos conectarnos a un router vía inalámbrica o vía cableada. 

Cuando nos conectamos al router, este nos asigna una dirección y nos permite realizar actividad en ciertos puertos. 

Estos dos elementos, dirección y puertos es algo muy importante para conocer la forma en la que se comporta el protocolo OSC. 

En resumen, podemos conectarnos a una red local para intercambiar información sin que esto necesariamente implique conectarnos a la web. 

Podriamos usar un router sin conexión a la red y podríamos hacer lo mismo (espero traer un router para hacer la prueba). 

Cuando nos conectamos a un router, éste nos asigna una dirección. Esta dirección es la que usaremos para comunicar mensajes. 

Por defecto, algunos programas utilizan ciertos puertos para comunicar cosas. Esta información también es importante, ya que es el canal por medio del cual enviaremos el mensaje. 

Entonces hay dos elementos a tener en cuenta la dirección y el puerto por el cuál enviaremos el mensaje. 

En caso de que no queramos enviar mensajes a otra computadora, esto puede realizarse sin que haya una conexión activa. 

Por defecto, la computadora establece una dirección específica que designa a la propia computadora que estamos utilizando:

127.0.0.1 o localhost o home. 

Si queremos hacer la conexión entre programas dentro de nuestra computadora, utilizaremos esta dirección.

Con esto, le indicaremos a la computadora que enviaremos mensajes internamente. 

Ejemplo de una dirección local con el puerto que por defecto lee SuperCollider para enviar mensajes OSC. 

```
127.0.0.1, 57120
```

### Mensajes OSC

El protocolo OSC fue creado para establecer la conexión de distintos dispositivos multimedia en una red, con este protocolo podemos mandar mensajes de comunicación.

Hay dos tipos de mensaje que se pueden enviar por medio del protocolo OSC, un tag o identificador que será la palabra con la cual distinguiremos lo que vamos a enviar y el mensaje en sí, que puede ser un número o varios números (entero o de punto flotante) un string o cadena de caracteres.

Ejemplo de un mensaje OSC con tag y tres parámetros

```
/posicionX, 100, 200.55, "mensaje entregado" 
```

Cabe destacar que el protocolo OSC sirve para comunicarse con otros dispositivos o computadoras, pero también para establecer una conexión local. 

La arquitectura de comunicación en SuperCollider parte de OSC para enviar mensajes a sí mismo.

## Comunicación local

El día de hoy vamos a ver que es posible realizar el intercambio de mensajes de OSC entre aplicaciones dentro de una misma computadora.

Vamos a hacer el ejercicio más sencillo: Cada que demos clic en la pantalla comunicaremos un mensaje OSC con las coordenadas en X y Y del mouse.

Por defecto Processing no utiliza clases para enviar/recibir OSC, así que lo primero que tenemos que hacer es instalar la librería oscP5.

Esto lo podemos hacer con el gestor de paquetes de Processing.

Luego vamos a preparar el sketch de Processing.

Entonces del lado de SuperCollider hay que hacer un lector de estos mensajes. 