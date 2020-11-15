# Cuarta sesión

Basado en: [Getting Started](http://doc.sccode.org/Tutorials/Getting-Started/)

[Para descargar SuperCollider](http://doc.sccode.org/Tutorials/Getting-Started/01-Introductory-Remarks.html)

El siguiente texto busca servir como una introducción a SuperCollider 3, un lenguaje de programación orientado a objetos para la síntesis de audio y el procesamiento de señales digitales (DSP). Este texto no asume un conocimiento previo en ciencias de la computaciones pero sí asume cierta familiaridad con la computadora y con un sistema operativo determinado, así como un conocimiento básico de acustica y audio digital).

## Combinaciones de teclas

Las combinaciones de teclas implican presionar una tecla y otra después. Por ejemplo "Ctrl-Enter" o "Cmd-Enter".

Ctrl y Cmd son equivalentes, la diferencia radica en el sistema operativo: ctrl se usa en windows y linux y cmd en mac.

Utilizaremos la combinación shift + Enter para declarar una línea de código. 

Utilizaremos la combinación ctrl/cmd + Enter para declarar secciones de código. 

## Qué es SuperCollider

La palabra SuperCpollider se utiliza para indicar distintas cosas:

1. Un servidor de audio

2. Un lenguaje de programación orientado al audio

3. Un intérprete para ese lenguaje, por ejemplo un programa capaz de interpretarlo.

4. El programa intérprete que funge como cliente para el servidor.

5. La aplicación que incluye los dos programas y que provee las funcionalidades mencionadas.

La aplicación SuperCollider está hecha de dos componentes distintos y autónomos: un servidor y un cliente. Para el primero tenemos la opción de elegir entre scsynth (SC-synthesizer) y supernova, para el segundo tenemos sclang (SC-languaje). 

Si descargamos la aplicación SC estaremos descargando un Entorno de Desarrollo Integrado que es el mismo para cualquier sistema operativo. En el IDE podemos destacar 3 ventanas: 1) el lugar en el que escribiremos el código, seguramente una ventana en blanco, 2) la *post window* que en cuanto abrimos SC imprime varias cosas y sirve para encontrar errores e imprimir mensajes y 3) Un menú con la documentación de SC. 

## Hola Mundo

Es una especie de tradición que cuando estamos aprendiendo un nuevo lenguaje de programación iniciamos con un programa simple: 'hello world'. Básicamente lo que queremos hacer es imprimir el texto 'Hello World!' en algún lugar.

Entonces lo que vamos a hacer es imprimir este texto en la ventana de información o *post window*. Para hacer esto escribimos en SC:

``java
"Hello World!".postln
``

Para ejecutar esto simplemente ponemos el curso en la misma línea del código que queremos ejecutar (puede ser en cualquier lugar de esa línea) y presionamos shift + Enter.

Si todo sale bien, deberíamos ver el mensaje impreso en la post window.

También podríamos seleccionar la línea de código que deseamos ejecutar y luego presionar ctrl+Enter.

Hablemos un poco del código. La primera parte "Hello World!" es una especie de objeto (podemos hablar de esto más adelante) llamado String. Un objeto es basicamente una forma de representar algo en la computadora, por ejemplo un texto o un oscilador. Podemos decir provisionalmente que un String es una forma de representar un pedazo de texto. También podemos decir que un String es un arreglo, colección o concatenación de caracteres.

La segunda parte .postln imprime el texto. Esta instrucción se puede aplicar a prácticamente cualquier cosa en SuperCollider y puede ser útil para imprimir mensajes o errores. 