# Octava sesión

Presumiblemente la última sesión. La idea es que podamos hablar de ciertas herramientas de transmisión pero antes, que resolvamos la propuesta de tocar el 19 de diciembre.

El 19 de diciembre sucederá un evento en el espacio virtual de PiranhaLab. Es un evento informal, muy parecido a las sesiones de live coding from scratch donde la idea es probar ideas y obtener retroalmentación.

Muchas veces el público son los mismos ejecutantes. 

¿En qué consiste tocar con la computadora? ¿Qué estándares ya existen para la realización de toquines vía streaming? 

¿Hay una estética de la música por computadora? Diversas aproximaciones. 

Comentar brevemente cómo ha sido el desarrollo de este espacio y cómo funciona, transmisión personalizada y espacio basado en Three.js

No es obligatorio tocar pero puede ser una buena oportunidad para probar todo esto.

Hay un espacio de una hora (puede ser más o menos), preguntar si alguien quiere tocar individualmente y preguntar si existen condiciones para tocar grupalmente.

También preguntar si alguien quiere tocar con audio e imagen o solo audio o solamente imagen.

Dependiendo de la respuesta podemos darle más peso a ciertas herramientas. De todas formas estaré explicando cada una de ellas 

## Audio solamente

Para transmitir audio solamente podemos utilizar un servidor icecast y transmitir desde butt.

En este caso es necesario un ruteador para enviar la señal de audio a butt. Según yo es posible realizar esto con jack, hay que probar en los distintos sistemas operativos. 

## Video solamente y audio y video

Para transmitir audio y video o video solamente podemos utilizar obs. En este caso es una forma muy parecida a cuando se transmite a youtube o twitch. 

Si utilizamos obs es relativamente fácil jalar audio y video desde el mismo obs y no necesitamos alguna especie de ruteador

## Audio compartido en una especie de jam

Este es el caso más complicado, no solamente necesitamos rutear el audio sino encontrar la forma de que alguna de las computadoras funcione como servidor. Para hacer esto necesitamos desbloquear puertos en la computadora.

Para hacer esto es posible utilizar jacktrip y sonobus. Sonobus es más fácil de usar pero jacktrip está más integrado.

