Ejecución de Processing, PDE, sketches. 

Variables, coloreado del código y componentes de un sketch de Processing.

## Funciones (en processing)

Las funciones son los los bloques basicos para construir programas en Processing. 

Algunas de ellas son *size()* *line()* *fill()* 

La modularidad es una de las características más importantes de las funciones en Processing. Son unidades de software independientes que pueden ser usadas para construir programas más complejos. 

Más adelante aprenderemos a escribir funciones para extender las capacidades de Processing más allá de sus características incorporadas. 

Imprimir en la consola. 

### Sistema de coordenadas

Recordemos que la pantalla de una computadora es una cuadrícula de elementos que emiten luz llamados pixeles.

Escribimos las coordenadas de un pixel de la siguiente manera: (x, y)

Si invocamos una pantalla de 200x200 pixeles, la esquina superior izquierda es el origen, o sea (0, 0) y la esquina inferior derecha es (199, 199)

¿En este ejemplo, qué coordenadas tendría el centro? 

### Formas

Mientras tanto, recordemos las formas básicas 

`line(x1, y1, x2, y2)`

Ejemplo: 

```java
size(480, 120);
line(20, 50, 420, 110);
```

Rectángulos...

`rect(x, y, anchura, altura)`

```java
// Dibujar un rectángulo con punto inicial en (180, 60), ancho de 220 y alto de 40
size(480, 120);
rect(180, 60, 220, 40);
```
Círculos...

`ellipse(x, y, width height)` 

```java
size(480, 120);
ellipse(278, -100, 400, 400);
```

Otras formas son: `triangle, quad` y `arc.` 

El sistema de coordenadas inicia arriba y a la izquierda ¿Por qué?

El orden de las instrucciones importa, en este ejemplo el rectángulo se dibuja encima del círculo debido a que aparece después en el código.

```java
size(480, 120);
ellipse(140, 0, 190, 190);
rect(160, 30, 260, 20);
```

En este otro, la elipse se encuentra encima debido a que aparece después 

```java
size(480, 120);
rect(160, 30, 260, 20);
ellipse(140, 0, 190, 190);
```

### `setup()` y `draw()`

Processing puede correr continuamente para dibujar o para interactuar en el tiempo. Para realizar esto, Processing tiene la función *draw()*. 

El código que se encuentra en *draw()* corre de arriba a abajo y se repite hasta que detienes el programa. Cada "vuelta" del *draw()* es un *frame*. 

Por *default* Processing corre a 60 fotogramas por segundo, esto quiere decir que hay 60 ciclos por segundo dentro del *draw()* 

```java
void draw() {
println("I'm drawing");
println(frameCount);
}
```

Processing también tiene una función llamada *setup()* que corre una vez que el programa inicia. 

## Condicionales

Las condicionales funcionan de manera parecida a las preguntas. Permiten a un programa realizar una acción si la respuesta a la pregunta es "cierto" o realizar otra acción si la respuesta es "falso". 

Las preguntas formuladas dentro de un programa son siempre declaraciones lógicas o relacionales. 

Por ejemplo, si la variable 'i' es igual a cero, dibuja una línea.

```java
void setup() {
size(240, 120);
strokeWeight(30);
}
void draw() {
background(204);
stroke(102);
line(40, 0, 70, height);
if (mousePressed) {
stroke(0);
} else {
stroke(255);
}
line(0, 70, width, 50);
}
```
## Loops

### `loop()` y `noLoop()`

Como ya vimos, Processing *loopea* continuamente el código escrito en `draw()`. Sin embargo, el *loop* `draw()` puede detenerse cuando escribimos `noLoop()`. En ese caso, el loop `draw()` puede reanudarse con `loop()`; 

Ejemplo: 

```java 
void setup() {
  size(200, 200);
  noLoop();  // draw() will not loop
}

float x = 0;

void draw() {
  background(204);
  x = x + .1;
  if (x > width) {
    x = 0;
  }
  line(x, 0, x, height); 
}

void mousePressed() {
  loop();  // Holding down the mouse activates looping
}

void mouseReleased() {
  noLoop();  // Releasing the mouse stops looping draw()
}
```

### `for()`

Otra estructura de código llamada `for()` hace posible correr una de código más de una vez. Esto permite condensar una repetición en pocas líneas. 

El siguiente ejemplo dibuja un patrón 

```java
size(480, 120);
strokeWeight(8);
line(20, 40, 80, 80);
line(80, 40, 140, 80);
line(140, 40, 200, 80);
line(200, 40, 260, 80);
line(260, 40, 320, 80);
line(320, 40, 380, 80);
line(380, 40, 440, 80);
```

Que puede simplificarse de la siguiente manera: 

```java
size(480, 120);
strokeWeight(8);
for (int i = 20; i < 400; i += 60) {
line(i, 40, i + 60, 80);
}
```

Las llaves, es decir { y }, distinguen a `for()`. El código que se encuentra entre llaves se llama bloque. Este es el código que va a ser repetido en cada iteración del *loop* `for()`. 

Dentro de los paréntesis hay tres declaraciones separadas por punto y coma. De izquierda a derecha, estas declaraciones son: *init, test* y *update*

```java
for (init; test; update) {
statements
}
```
En *init* fijamos el valor inicial, muchas veces declarando una variable que usaremos dentro del loop for. 

El nombre de variable `i` es frecuentemente usado, pero no hay nada especial en él. 

*Test* evalúa el valor de esta variable (para el caso del primer código, revisa si `i` sigue siendo menor que 400). *Update* cambia el valor de la variable, agregando 60 antes de repetir el *loop*.

Un diagrama puede clarificar el flujo de un *for loop* 

Cabe destacar que la declaración *text* es siempre una expresión relacional que compara dos valores con un operador relacional. En el ejemplo de arriba, la expresión es "i < 400" y el operador es < (menor que). Los operadores relacionales más comunes son: 

| Símbolo | Operación        |
|:-------:|:----------------:|
| >       | Mayor que        | 
| <       | Menor que        |
| >=      | Mayor o igual que|
| <=      | Menor que        |
| ==      | Igual a          |
| !=      | No es igual a    |

El resultado de la evaluación siempre es cierto o falso. 

## Loops

### `while()`

Controla una secuencia de repeticiones. La estructura `while()` ejecuta continuamente una serie de declaraciones mientras que la evaluación de la expresión se mantiene en cierto. 

```java	
while (expression) {
  statements
}
```

La expresión puede ser "peligrosa" debido a que el código dentro del *loop while* no terminará hasta que la expresión dentro de *while* se convierta en falsa.

Ejemplo: 

```java
int i = 0;
while (i < 80) {
  line(30, i, 80, i);
  i = i + 5;
}
```

## Color

Hasta el momento hemos dibujado formas en blanco y negro y el fondo de la ventana se ha mantenido en gris claro. 

Para cambiar esto vamos a utilizar las funciones `background()` `fill` y `stroke`. 

Los valores de los parámetros tienen el rango de 0 a 255, donde 255 es blanco, 128 es un gris medio y 0 es negro. 

El siguiente ejemplo muestra tres diferentes valores en circulos que están sobre un fondo negro. 

```java
size(480, 120);
background(0); // negro
fill(204); // gris claro
ellipse(132, 82, 200, 200); // círculo gris claro
fill(153); // gris medio 
ellipse(228, -16, 200, 200); // círculo gris medio
fill(102); // gris oscuro
ellipse(268, 118, 200, 200); círculo gris oscuro
```

Es posible deshabilitar el contorno y el relleno con `noStroke()` y `noFill()`. 

```java
size(480, 120);
fill(153);
ellipse(132, 82, 200, 200);
noFill();
ellipse(228, -16, 200, 200);
noStroke();
ellipse(268, 118, 200, 200);
```

Si queremos usar valores más allá de la escala de grises, podemos usar tres parámetros para especificar los componentes de un color (rojo, verde y azu). 

```java
size(480, 120);
noStroke();
background(0, 26, 51);
fill(255, 0, 0);
ellipse(132, 82, 200, 200);
fill(0, 255, 0);
ellipse(228, -16, 200, 200);
fill(0, 0, 255);
ellipse(268, 118, 200, 200);
```

La definición de un color con la convención RGB proviene de la manera en que la computadora define colores en la pantalla. 

Los valores RGB se pueden definir en un rango que va de 0 a 255. 

Hay un cuarto valor que se puede utilizar para definir un valor de color. El valor alpha define transparencia. 

Este valor, como los que hemos visto hasta el momento, puede ir de 0 a 255 donde 0 define un color completalmente transparente y 255 un color completamente opaco. 

```java
size(480, 120);
noStroke();
background(204, 226, 225);
fill(255, 0, 0, 160);
ellipse(132, 82, 200, 200);
fill(0, 255, 0, 160);
ellipse(228, -16, 200, 200); 
27fill(0, 0, 255, 160);
ellipse(268, 118, 200, 200);
```
Otras formas de definir el color. 

## Aleatoriedad

Las computadoras pueden generar valores y comportamientos líneales muy facilmente. Sin embargo, el mundo físico se comporta de maneras diversas, muchas veces alejadas de ese comportamiento lineal. 

Es posible simular comportamientos y cualidad inpredecibles al generar números aleatorios. 

En Processing, una función que puede realizar esto es la función `random()` 

Antes de dibujar...

```java
void draw() {
float r = random(0, mouseX);
println(r);
}
```

El ejemplo anterior imprime valores aleatorios en la Consola, en un rango que está limitado por la posición del mouse en el eje X. 

La función `random()` siempre devuelve un valor de punto flotante. Hay que asegurarse que la variable declarada sea un número de punto flotante. Esto se puede determinar con `float`

El siguiente ejemplo usa los valores que genera `random()` para cambiar la posición de las líneas en la pantalla. Si el mouse se encuentra a la izquierda de la pantalla, el cambio es pequeño, si se mueve a la derecha, el valor se incrementa y el cambio es más notorio. 

```java
void setup() {
size(240, 120);
}
void draw() {
background(204);
for (int x = 20; x < width; x += 20) {
float mx = mouseX / 10;
float offsetA = random(-mx, mx);
float offsetB = random(-mx, mx);
line(x + offsetA, 20, x - offsetB, 100);
}
}
```

Si generamos valores alteatorios para mover objetos, la imagen resultante puede ser, aparentemente, más "natural". En el siguiente ejemplo, la posición del círculo se modifica por valores aleatorios en cada vuelta del `draw`. Debido a que el `background` no está declarado ni se actualiza en `draw()`, las posiciones anteriores permanecen dibujadas. 

```java
float speed = 2.5;
int diameter = 20;
float x;
float y;
void setup() {
size(240, 120);
x = width/2;
y = height/2;
}
void draw() {
x += random(-speed, speed);
y += random(-speed, speed);
ellipse(x, y, diameter, diameter);
}
```

## Transformaciones 

### translate(), rotate() y scale()

La función translate sirve para cambiar el sistema de coordenadas, por default (0, 0) a una localización diferente. 


```java
void setup() {
size(120, 120);
}
void draw() {
translate(mouseX, mouseY);
rect(0, 0, 30, 30);
}
```

Para el caso del ejemplo anterior, el sistema de coordenadas cambia de (0, 0) a la posición del mouse. cada vez que draw() dibuja algo, rect() se dibuja en el nuevo origen

La función rotate() rota el sistema de coordenadas. Tiene un solo parámetro, que es el ángulo (en radianes) de rotación. Su rotación es relativa a (0, 0), es decir, rota alrrededor del origen. 

```java
void setup() {
size(120, 120);
}
void draw() {
rotate(mouseX / 100.0);
rect(40, 30, 160, 20);
}
```

Es posible utilizar una función para convertir grados sexagesimales a radianes: radians(). Esta función toma el ángulo en grados y los cambia a su valor equivalente en radianes. 

Para usar las medidas en grados y no en radianes.

```java
void setup() {                                                                                                                                                                                
size(520, 520);                                                                                                                                                                               
}                                                                                                                                                                                             
void draw() {                                                                                                                                                                                 
rotate(radians(mouseX % 360));                                                                                                                                                                
rect(140, 130, 160, 20);                                                                                                                                                                      
} 
```

La transformación `scale()` cambia el tamaño de la figura seleccionada. Debido a que las coordenadas expanden o contraen en la medida que la escala cambia, todo lo que se dibuja en la ventana aumenta o disminuye proporcionalmente. Usamos scale(1.5) para aumentar todo a 150% de su tamaño original. 


```java
void setup() {
size(120, 120);
}

void draw() {
translate(mouseX, mouseY);
scale(mouseX / 60.0);
rect(-15, -15, 30, 30);
}
```


### `pushMatrix() y popMatrix()`

Para aislar los efectos de una transformación de forma tal que no afecten a otros comandos, usamos las funciones `pushMatrix()` y `popMatrix()`

Cuando `pushMatrix()` está corriendo, salva una copia del sistema de coordenadas que está en ejecución y reanuda ese sistema después de `popMatrix()`; 

Esto es útil cuando requerimos hacer transformaciones para una figura, pero no queremos que tenga consecuencias para otras. 

```java
void setup() {
size(120, 120);
}
void draw() {
pushMatrix();
translate(mouseX, mouseY);
rect(0, 0, 30, 30);
popMatrix();
translate(35, 10);
rect(0, 0, 15, 15);
}
```

Para rotar una figura en su propio eje: 

```java
void setup() {
size(120, 120);
}
void draw() {
rotate(mouseX / 100.0);
rect(40, 30, 160, 20);
}
```

### Operadores aritméticos

En términos de código, símbolos como +, - y * son operadores. Cuando aparecen entre dos valores, crean una expresión. 

Por ejemplo 5 + 9 y 1024 - 512 son ambas experesiones. 

Los operadores para realizar operaciones matemáticas básicas son: 

| Símbolo | Operación        |
|:-------:|:----------------:|
| +       | Suma             | 
| -       | Resta            |
| *       | Multiplicación   |
| /       | División         |
| =       | Igual a          |

Processing tiene una serie de reglas para definir que operadores tienen preferencia. Esto quiere decir que algunos cálculos se hacen primero, luego otros y luego otros. 

Estas reglas definen el orden de declaración del código cuando se ejecuta. 

Ejemplo:

```java
int x = 4 + 4 * 5; 
```

En este caso la operación 4 * 5 se evalúa primero debido a que la multiplicación tiene la prioridad más alta. Posteriormente, al producto de 4 * 5 se le agrega 4. 

Para forzar el orden de las operaciones se utilizan los paréntesis. Todo lo que está entre paréntesis se calcula primero. 

|
```java
int x = (4 + 4) * 5; 
```

Otros tipos de operaciones que son convenciones para ahorrar escritura: 

```java
x += 10; // es igual a x = x +10 
```

```java
x ++; // es igual a x = x + 1 
```