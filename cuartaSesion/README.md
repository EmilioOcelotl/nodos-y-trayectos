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

La palabra Supercollider se utiliza para indicar distintas cosas:

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

``
"Hello World!".postln
``

Para ejecutar esto simplemente ponemos el curso en la misma línea del código que queremos ejecutar (puede ser en cualquier lugar de esa línea) y presionamos shift + Enter.

Si todo sale bien, deberíamos ver el mensaje impreso en la post window.

También podríamos seleccionar la línea de código que deseamos ejecutar y luego presionar ctrl+Enter.

Hablemos un poco del código. La primera parte "Hello World!" es una especie de objeto (podemos hablar de esto más adelante) llamado String. Un objeto es basicamente una forma de representar algo en la computadora, por ejemplo un texto o un oscilador. Podemos decir provisionalmente que un String es una forma de representar un pedazo de texto. También podemos decir que un String es un arreglo, colección o concatenación de caracteres.

La segunda parte .postln imprime el texto. Esta instrucción se puede aplicar a prácticamente cualquier cosa en SuperCollider y puede ser útil para imprimir mensajes o errores.

## Coloreado

Hay distintos tipos de coloreado dependiendo de lo que escribamos en SuperCollider.

Por defecto los strings se colorean de gris, el texto general en negro. Veamos que pasa con los comentarios

``
// esto es una línea comentada

/*

Esto es un comentario
multilinea

*/
``

Los distintos elementos de SC se colorean de manera distinta, más adelante veremos el caso de las palabras que empiezan con mayúsculas o clases

## Operaciones y variables

En SC es posible realizar operaciones aritméticas declarando cada línea.

``
54 + 34;
234 / 2;
95 * 23;
63 - 22;  
``

Más adelante veremos que estas operaciones se pueden realizar para cualquier tipo de dato. Cuando hablamos de tipo de dato nos referimos a números, strings o cadenas de caractéres, funciones o inicluso a sintetizadores.

Una de las características de SC como lenguaje de programación es el uso de varibles. Las variables son espacios en la memoria de la computadora donde podemos almacenar cosas, prácticamente cualquier tipo de dato que SC pueda leer.

Podemos distinguir variables globales de variables locales. Más adelante analizaremos el uso de variables locales, mientras tanto, revisemos el caso de las variables globales.

Las variables pueden modicarse dinámicamente, usarse en cualquier otro momento del programa que estemos contruyendo y también pueden usarse más de una vez.

Las variables globales funcionan en cualquier momento del código o de lo que declaremos en SC. La forma más sencilla de usar variables globales es con el uso de letras sueltas.

``
a = 54;
a;
b = "hola mundo";
b;
b.postln;
c = 23 + 67; 
d = a + b;
``

El último caso muestra que es posible asignar operaciones sobre variables globales para asignar una nueva variable local.

Es importante tener en cuenta que hay una letra en específico que está asignada por defecto al servidor: la letra s.

Es posible utilizar variables que tengan varios caracteres si escribimos el caracter ~ + el nombre de la variable.

``
~miVariable = 78;
``

## Sonido y el servidor 
