# UD01- Introducción a Javascript

**Tabla de contenidos**

   * [1. Introducción](#1-introducción)
      + [1.1 Un poco de historia](#11-un-poco-de-historia)
      + [1.2 Soporte en los navegadores](#12-soporte-en-los-navegadores)
      + [1.3 Herramientas](#13-herramientas)
         - [1.3.1 La consola del navegador](#131-la-consola-del-navegador)
         - [1.3.2 Editores](#132-editores)
         - [1.3.3 Editores on-line](#133-editores-on-line)
         - [1.3.4 npm](#134-npm)
         - [1.3.5 git](#135-git)
      + [1.4 Incluir javascript en una página web](#14-incluir-javascript-en-una-página-web)
      + [1.5 Mostrar información](#15-mostrar-información)
   * [2. Sintaxis](#2-sintaxis)
      + [2.1 Variables](#21-variables)
      + [2.2 Funciones](#22-funciones)
         - [2.2.1 Parámetros](#221-parámetros)
         - [2.2.2 Funciones anónimas](#222-funciones-anónimas)
         - [2.2.3 Arrow functions (funciones _lambda_)](#223-arrow-functions-funciones-_lambda_)
      + [2.3 Estructuras y bucles](#23-estructuras-y-bucles)
         - [2.3.1 Estructura condicional: if](#231-estructura-condicional-if)
         - [2.3.2 Estructura condicional: switch](#232-estructura-condicional-switch)
         - [2.3.3 Bucle _while_](#233-bucle-_while_)
         - [2.3.4 Bucle: for](#234-bucle-for)
            * [2.3.4.1 Bucle: for con contador](#2341-bucle-for-con-contador)
            * [2.3.4.2 Bucle: for...in](#2342-bucle-forin)
            * [2.3.4.3 Bucle: for...of](#2343-bucle-forof)
      + [2.4 Tipos de datos básicos](#24-tipos-de-datos-básicos)
         - [2.4.1 Casting de variables](#241-casting-de-variables)
         - [2.4.2 Number](#242-number)
         - [2.4.3 String](#243-string)
            * [2.4.3.1 Template literals](#2431-template-literals)
         - [2.4.4 Boolean](#244-boolean)
   * [3. Manejo de errores](#3-manejo-de-errores)
   * [4. Buenas prácticas](#4-buenas-prácticas)
      + [4.1 'use strict'](#41-use-strict)
      + [4.2 Variables](#42-variables)
      + [4.3 Errores](#43-errores)
      + [4.4 Otras](#44-otras)
      + [4.5 Clean Code](#45-clean-code)

- [Bibliografía](#bibliografía)

## 1. Introducción
En las páginas web el elemento fundamental es el fichero HTML con la información a mostrar en el navegador. Posteriormente surgió la posibilidad de "decorar" esa información para mejorar su apariencia, lo que dio lugar al CSS. Y también se pensó en dar dinamismo a las páginas y apareció el lenguaje Javascript.

En un primer momento las 3 cosas estaban mezcladas en el fichero HTML pero eso complicaba bastante el poder leer esa página a la hora de mantenerla por lo que se pensó en separar los 3 elementos básicos:
- HTML: se encarga de estructurar la página y proporciona su información, pero es una información estática
- CSS: es lo que da forma a dicha información, permite mejorar su apariencia, permite que se adapte a distintos dispositivos, ...
- Javascript: es el que da vida a un sitio web y le permite reaccionar a las acciones del usuario

Por tanto nuestras aplicaciones tendrán estos 3 elementos y lo recomendable es que estén separados en distintos ficheros:
- El HTML lo tendremos habitualmente en un fichero index.html, normalmente en una carpeta llamada _public_
- El CSS lo tendremos en uno o más ficheros con extensión _.css_ dentro de una carpeta llamada _styles_
- EL JS estará en ficheros con extensión _.js_ en un directorio llamado _scripts_

Las características principales de Javascript son:
- Es un lenguaje interpretado, no compilado
- Se ejecuta en el lado cliente (en un navegador web), aunque hay implementaciones como NodeJS para el lado servidor
- Es un lenguaje orientado a objetos (podemos crear e instanciar objetos y usar objetos predefinidos del lenguaje) pero basado en prototipos (por debajo un objeto es un prototipo y nosotros podemos crear objetos sin instanciarlos, haciendo copias del prototipo)
- Se trata de un lenguaje débilmente tipado, con tipificación dinámica (no se indica el tipo de datos de una variable al declararla e incluso puede cambiarse)

Lo usaremos para:
* Cambiar el contenido de la página
* Cambiar los atributos de un elemento
* Cambiar la apariencia de algo
* Validar datos de formularios
* ...

Sin embargo, por razones de seguridad, Javascript no nos permite hacer cosas como:
* Acceder al sistema de ficheros del cliente
* Capturar datos de un servidor (puede pedirlo y el servidor se los servirá, o no)
* Modificar las preferencias del navegador
* Enviar e-mails de forma invisible o crear ventanas sin que el usuario lo vea
* ...

### 1.1 Un poco de historia
Javascript es una implementación del lenguaje **ECMAScript** (el estándar que define sus características). El lenguaje surgió en 1997 y todos los navegadores a partir de 2012 soportan al menos la versión **ES5.1** completamente. En 2015 se lanzó la 6ª versión, inicialmente llamada **ES6** y posteriormente renombrada como **ES2015**, que introdujo importantes mejoras en el lenguaje y que es la versión que usaremos nosotros. Desde entonces van saliendo nuevas versiones cada año que introducen cambios pequeños. La última es la **ES2022** aprobada en Junio de 2022.

Las principales mejoras que introdujo ES2015 son: clases de objetos, let, for..of, Map, Set, Arrow functions, Promesas, spread, destructuring, ...

### 1.2 Soporte en los navegadores
Los navegadores no se adaptan inmediatamente a las nuevas versiones de Javascript por lo que puede ser un problema usar una versión muy moderna ya que puede haber partes de los programas que no funcionen en los navegadores de muchos usuarios. En la página de [_Kangax_](https://kangax.github.io/compat-table/es6/) podemos ver la compatibilidad de los diferentes navegadores con las distintas versiones de Javascript. También podemos usar [_CanIUse_](https://caniuse.com/) para buscar la compatibilidad de un elemento concreto de Javascript así como de HTML5 o CSS3. 

Si queremos asegurar la máxima compatibilidad debemos usar la versión ES5 (pero nos perdemos muchas mejoras del lenguaje) o mejor, usar la ES6 (o posterior) y después _transpilar_ nuestro código a la version ES5. De esto se ocupan los _transpiladores_ (**Babel** es el más conocido) por lo que no suponen un esfuerzo extra para el programador.

### 1.3 Herramientas
#### 1.3.1 La consola del navegador
Es la herramienta que más nos va a ayudar a la hora de depurar nuestro código. Abrimos las herramientas para el desarrollador (en Chrome y Firefox pulsando la tecla _F12_) y vamos a la pestaña _Consola_:

Allí vemos mensajes del navegador como errores y advertencias que genera el código y todos los mensajes que pongamos en el código para ayudarnos a depurarlo (cusando los comandos **console.log** y **console.error**).

Además en ella podemos escribir instrucciones Javascript que se ejecutarán mostrando su resultado. También la usaremos para mostrar el valor de nuestras variables y para probar código que, una vez que funcione correctamente, lo copiaremos a nuestro programa.

> **EJERCICIO 1_UD1**: abre la consola y prueba las funciones _alert_, _confirm_ y _prompt_.

Siempre depuraremos los programas desde aquí (ponemos puntos de interrupción, vemos el valor de las variables, ...).

#### 1.3.2 Editores
Podemos usar el que más nos guste, desde editores tan simples como NotePad++ hasta complejos IDEs. La mayoría soportan las últimas versiones de la sintaxis de Javascript (Netbeans, Eclipse, Visual Studio, Sublime, Atom, Kate, Notepad++, ...). Vamos a utilizar [**Visual Studio Code**](https://code.visualstudio.com/) por su sencillez y por los plugins que incorpora para hacer más cómodo el trabajo. En _Visual Studio Code_ instalaremos algún _plugin_ como:
- SonarLint: es más que un _linter_ e informa de todo tipo de errores pero también del código que no cumple las recomendaciones (incluye gran número de reglas). Marca el código mientras lo escribimos y además podemos ver todas las advertencias en el panel de Problemas.
- Vetur: lo instalaremos en el segundo bloque. Necesario para trabajar con los ficheros de _Vue_

#### 1.3.3 Editores on-line
Son muy útiles porque permiten ver el código y el resultado a la vez. Normalmente tienen varias pestañas o secciones de la página donde poner el código HTML, CSS yJavascript y ver su resultado. 

Algunos de los más conocidos son [Codesandbox](https://codesandbox.io/), [Fiddle](https://jsfiddle.net), [Plunker](https://plnkr.co), [CodePen](https://codepen.io/pen/), ...aunque hay muchos más.

> Ejemplo de 'Hello World' en CodePen:

<p class="codepen" data-height="265" data-theme-id="0" data-default-tab="js,result" data-user="kscatcensus" data-slug-hash="XedLvZ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Hello World Codepen">
  <span>See the Pen <a href="https://codepen.io/kscatcensus/pen/XedLvZ/">
  Hello World Codepen</a> by Kevin Schweickhardt (<a href="https://codepen.io/kscatcensus">@kscatcensus</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

#### 1.3.4 npm
**npm** es el gestor de paquetes del framework Javascript **Node.js** y suele utilizarse en programación *frontend* como gestor de dependencias de la aplicación. Esto significa que será la herramienta que se encargará de descargar y poner a disposición de nuestra aplicación todas las librerías Javascript que vayamos a utilizar, por ejemplo para hacer los tests de nuestros programas (en algunas prácticas haremos o pasaremos tests unitarios ya hechos para comprobar que nuestros programas funcionan correctamente y, sobre todo, que continúan haciéndolo tras realizar alguna modificación en ellos).

Para instalar _npm_ tenemos que instalar _NodeJS_. Podemos instalarlo desde los repositorios como cualquier otro programa (`apt install nodejs`), pero posiblemente nos instalará una versión poco actualizada por lo que es mejor instalarlo desde [NodeSource](https://nodejs.org/es/download/package-manager/#distribuciones-de-linux-basadas-en-debian-y-ubuntu) siguiendo las instrucciones que allí se indican, que básicamente son ejecutar:

```bash
curl -sL https://deb.nodesource.com/setup_X.y | sudo -E bash -
sudo apt-get install -y nodejs
```

(cambiaremos X.y por la versión que queramos, normalmente la últma versión estable).

También podemos descargarlo directamente desde [NodeJS.org](https://nodejs.org/es/download/), descomprimir el paquete e instalarlo (`dpkg -i _nombre_del_paquete_`).

Con eso ya tendremos _npm_ en nuestro equipo. Podemos comprovar la versión que tenemos con:
```bash
npm -v
```

#### 1.3.5 git
Usaremos repositorios para poder realizar el control de versiones. Para instalarlo simplemente habrá que instalar el paquete _git_ (`apt-get install git`).

Podemos gestionar git desde la consola o se puede instal·ar una extensión per a utilizarlo desde el entorno de programación. En el caso de Visual Studio lo encontramos en
[https://code.visualstudio.com/docs/editor/versioncontrol](https://code.visualstudio.com/docs/editor/versioncontrol).

### 1.4 Incluir javascript en una página web
El código Javascript va entre etiquetas _\<script>_. Puede ponerse en el _\<head>_ o en el _\<body>_. Funciona como cualquier otra etiqueta y el navegador la interpreta cuando llega a ella (va leyendo y ejecutando el fichero línea a línea). Podéis ver en [este vídeo](https://www.youtube.com/watch?v=AQn22gjtSWQ&list=PLI7nHlOIIPOJtTDs1HVJABswW-xJcA7_o&index=2) un ejemplo muy simple de cómo se ejecuta el código en el HEAD y en el BODY.

Lo mejor en cuanto a rendimiento es ponerla al final del _\<body>_ para que no se detenga el renderizado de la página mientras se descarga y se ejecuta el código. También podemos ponerlo en el \<head> pero usando los atributos **async** y/o **defer** (en Internet encontraréis mucha información sobre esta cuestión, por ejemplo [aquí](https://somostechies.com/async-vs-defer/)).

Como se ve en el primer vídeo, es posible poner el código directamente entre la etiqueta _\<script>_  y su etiqueta de finalización pero lo correcto es que esté en un fichero externo (con extensión **.js**) que cargamos mediante el atributo _src_ de la etiqueta. Así conseguimos que la página HTML cargue más rápido (si lo ponemos al final del BODY o usamos _async_) y además no mezclar HTML y JS en el mismo fichero, lo mejora la legibilidad del código y facilita su mantenimento:
```html
<script src="./scripts/main.js"></script>
```

### 1.5 Mostrar información
Javascript permite mostrar al usuario ventanas modales para pedirle o mostrarle información. Las funciones que lo hacen son:
* `window.alert(mensaje)`: Muesta en una ventana modal _mensaje_ con un botón de _Aceptar_ para cerra la ventana.
* `window.confirm(mensaje)`: Muesta en una ventana modal _mensaje_ con botones de _Aceptar_ y _Cancelar_. La función devuelve **true** o **false** en función del botón pulsado por el usuario.
* `window.prompt(mensaje [, valor predeterminado])`: Muesta en una ventana modal _mensaje_ y debajo tiene un campo donde el usuario puede escribir, junto con botones de _Aceptar_ y _Cancelar_. La función devuelve el valor introducido por el usuario como texto (es decir que si introduce 54 lo que se obtiene es "54") o **false** si el usuario pulsa _Cancelar_.

También se pueden escribir las funciones sin _window._ (es decir `alert('Hola')` en vez de `window.alert('Hola')`) ya que en Javascript todos los métodos y propiedades de los que no se indica de qué objeto son se ejecutan en el objeto _window_.

Si queremos mostrar una información para depurar nuestro código no utilizaremos _alert(mensaje)_ sino `console.log(mensaje)` o `console.error(mensaje)`. Estas funciones muestran la información pero en la consola del navegador. La diferencia es que _console.error_ la muestra como si fuera un error de Javascript.

## 2. Sintaxis

### 2.1 Variables

Javascript es un lenguaje débilmente tipado. Esto significa que no se indica de qué tipo es una variable al declararla e incluso puede cambiar su tipo a lo largo de la ejecución del programa. Ejemplo:

```javascript
let miVariable;         // declaro miVariable y como no se asigno un valor valdrá undefined
miVariable='Hola';      // ahora su valor es 'Hola', por tanto contiene una cadena de texto
miVariable=34;          // pero ahora contiene un número
miVariable=[3, 45, 2];  // y ahora un array
miVariable=undefined;   // para volver a valer el valor especial undefined
```

> **EJERCICIO 2_UD1**: Ejecuta en la consola del navegador las instrucciones anteriores y comprueba el valor de miVariable tras cada instrucción (para ver el valor de una variable simplemente ponemos en la consola su nombre: `miVariable`

Ni siquiera estamos obligados a declarar una variable antes de usarla, aunque es recomendable para evitar errores que nos costará depurar. Podemos hacer que se produzca un error si no declaramos una variable incluyendo al principio de nuestro código la instrucción

```javascript
'use strict'
```

Las variables de declaran con **let** (lo recomendado desde ES2015), aunque también pueden declararse con **var**. La diferencia es que con _let_ la variable sólo existe en el bloque en que se declara mientras que con _var_ la variable existe en toda la función en que se declara:

```javascript
if (edad < 18) {
  let textoLet = 'Eres mayor de edad';
  var textoVar = 'Eres mayor de edad';
} else {
  let textoLet = 'Eres menor de edad';
  var textoVar = 'Eres menor de edad';
}
console.log(textoLet);  // mostrará undefined porque fuera del if no existe la variable
console.log(textoVar);  // mostrará la cadena
```

Cualquier variable que no se declara dentro de una función (o si se usa sin declarar) es _global_. Debemos siempre intentar NO usar variables globales.

Se recomienda que Los nombres de las variables sigan la sintaxis _camelCase_ (ej.: _miPrimeraVariable_).

Desde ES2015 también podemos declarar constantes con **const**. Se les debe dar un valor al declararlas y si intentamos modificarlo posteriorment se produce un error.

NOTA: en la página de [Babel](https://babeljs.io/) podemos teclear código en ES2015 y ver cómo quedaría una vez transpilado a ES5.

### 2.2 Funciones

Se declaran con **function** y se les pasan los parámetros entre paréntesis. La función puede devolver un valor usando **return** (si no tiene _return_ es como si devolviera _undefined_). 

Puede usarse una función antes de haberla declarado por el comportamiento de Javascript llamado _hoisting_: el navegador primero carga todas las funciones y mueve las declaraciones de las variables al principio y luego ejecuta el código.

> **EJERCICIO 3_UD1**: Haz una función que te pida que escribas algo y muestre un alert diciendo 'Has escrito...' y el valor introducido. Pruébala en el proyecto JS Base.

#### 2.2.1 Parámetros

Si se llama una función con menos parámetros de los declarados el valor de los parámetros no pasados será _undefined_:

```javascript
function potencia(base, exponente) {
    console.log(base);            // muestra 4
    console.log(exponente);       // muestra undefined
    let valor=1;
    for (let i=1; i<=exponente; i++) {
      valor=valor*base;
    }
    return valor;
}

potencia(4);    // devolverá 1 ya que no se ejecuta el for
```

Podemos dar un **valor por defecto** a los parámetros por si no los pasan asignándoles el valor al definirlos:

```javascript
function potencia(base, exponente=2) {
    console.log(base);            // muestra 4
    console.log(exponente);       // muestra 2 la primera vez y 5 la segunda
    let valor=1;
    for (let i=1; i<=exponente; i++) {
      valor=valor*base;
    }
    return valor;
}

console.log(potencia(4));         // mostrará 16 (4^2)
console.log(potencia(4,5));       // mostrará 1024 (4^5)
```

> NOTA: En ES5 para dar un valor por defecto a una variable se hacía
>
> ```javascript
> function potencia(base, exponente) {
>  exponente = exponente || 2;       // si exponente vale undefined se la asigna el valor 2
> ...
> ```

También es posible acceder a los parámetros desde el array **arguments[]** si no sabemos cuántos recibiremos:

```javascript
function suma () {
    var result = 0;
    for (var i=0; i<arguments.length; i++)
        result += arguments[i];
    return result;
}

console.log(suma(4, 2));                    // mostrará 6
console.log(suma(4, 2, 5, 3, 2, 1, 3));     // mostrará 20
```

En Javascript las funciones son un tipo de datos más por lo que podemos hacer cosas como pasarlas por argumento o asignarlas a una variable:

```javascript
const cuadrado = function(value) {
  return value * value
}
function aplica_fn(dato, funcion_a_aplicar) {
    return funcion_a_aplicar(dato);
}

aplica_fn(3, cuadrado);     // devolverá 9 (3^2)
```

A este tipo de funciones se llama _funciones de primera clase_ y son típicas de lenguajes funcionales.

#### 2.2.2 Funciones anónimas

Como acabamos de ver podemos definir una función sin darle un nombre. Dicha función puede asignarse a una variable, autoejecutarse o asignasrse a un manejador de eventos. Ejemplo:

```javascript
let holaMundo = function() {
    alert('Hola mundo!');
}

holaMundo();        // se ejecuta la función
```

Como vemos asignamos una función a una variable de forma que podamos "ejecutar" dicha variable.

#### 2.2.3 Arrow functions (funciones _lambda_)

ES2015 permite declarar una función anónima de forma más corta. Ejemplo sin _arrow function_:

```javascript
let potencia = function(base, exponente) {
    let valor=1;
    for (let i=1; i<=exponente; i++) {
      valor=valor*base;
    }
    return valor;
}
```

Al escribirla con la sintaxis de una _arrow function_ lo que hacemos es:

* Eliminamos la palabra _function_
* Si sólo tiene 1 parámetro podemos eliminar los paréntesis de los parámetros
* Ponemos el símbolo _=>_
* Si la función sólo tiene 1 línea podemos eliminamr las { } y la palabra _return_

El ejemplo con _arrow function_:

```javascript
let potencia = (base, exponente) => {
    let valor=1;
    for (let i=1; i<=exponente; i++) {
      valor=valor*base;
    }
    return valor;
}
```

Otro ejemplo, sin _arrow function_:

```javascript
let cuadrado = function(base) {
    return base * base;
}
```

conn _arrow function_:

```javascript
let cuadrado = base => base * base;
```

> **EJERCICIO 4_UD1**: Haz una _arrow function_ que devuelva el cubo del número pasado como parámetro y pruébala desde nuestro proyecto JS Base. Escríbela primero en la forma habitual y luego la "traduces" a _arrow function_.

### 2.3 Estructuras y bucles

#### 2.3.1 Estructura condicional: if

El **if** es como en la mayoría de lenguajes. Puede tener asociado un **else** y pueden anidarse varios con **else if**.

```javascript
if (condicion) {
    ...
} else if (condicion2) {
    ...
} else if (condicion3) {
    ...
} else {
    ...
}
```

Ejemplo:

```javascript
if (edad < 18) {
    console.log('Es menor de edad');
} else if (edad > 65) {
    console.log('Está jubilado');
} else {
    console.log('Edad correcta');
}
```

Se puede usar el operador **? :** que es como un _if_ que devuelve un valor:

```javascript
let esMayorDeEdad = (edad>18)?true:false;
```

#### 2.3.2 Estructura condicional: switch

El **switch** también es como en la mayoría de lenguajes. Hay que poner _break_ al final de cada bloque para que no continúe evaluando:

```javascript
switch(color) {
    case 'blanco':
    case 'amarillo':    // Ambos colores entran aquí
        colorFondo='azul';
        break;
    case 'azul':
        colorFondo='amarillo';
        break;
    default:            // Para cualquier otro valor
        colorFondo='negro';
}
```

Javascript permite que el _switch_ en vez de evaluar valores pueda evaluar expresiones. En este caso se pone como condición _true_:

```javascript
switch(true) {
    case age < 18:
        console.log('Eres muy joven para entrar');
        break;
    case age < 65:
        console.log('Puedes entrar');
        break;
    default:
        console.log('Eres muy mayor para entrar');
}
```

#### 2.3.3 Bucle _while_

Podemos usar el bucle _while...do_

```javascript
while (condicion) {
    // sentencias
}
```

que se ejecutará 0 o más veces. Ejemplo:

```javascript
let nota=prompt('Introduce una nota (o cancela para finalizar)');
while (nota) {
    console.log('La nota introducida es: '+nota);
    nota=prompt('Introduce una nota (o cancela para finalizar)');
}
```

O el bucle _do...while_:

```javascript
do {
    // sentencias
} while (condicion)
```

que al menos se ejecutará 1 vez. Ejemplo:

```javascript
let nota;
do {
    nota=prompt('Introduce una nota (o cancela para finalizar)');
    console.log('La nota introducida es: '+nota);
} while (nota)
```

> **EJERCICIO 5_UD1**: Haz un programa para que el usuario juegue a adivinar un número. Obtén un número al azar (busca por internet cómo se hace o simplemente guarda el número que quieras en una variable) y ve pidiendo al usuario que introduzca un número. Si es el que busca le dices que lo ha encontrado y si no le mostrarás si el número que busca el mayor o menor que el introducido. El juego acaba cuando el usuario encuentra el número o cuando pulsa en 'Cancelar' (en ese caso le mostraremos un mensaje de que ha cancelado el juego).

#### 2.3.4 Bucle: for

Tenemos muchos _for_ que podemos usar.

##### 2.3.4.1 Bucle: for con contador

Creamos una variable contador que controla las veces que se ejecuta el for:

```javascript
let datos=[5, 23, 12, 85]
let sumaDatos=0;

for (let i=0; i<datos.length; i++) {
    sumaDatos += datos[i];
}  
// El valor de sumaDatos será 125
```

> **EJERCICIO 6_UD1**: El factorial de un número entero n es una operación matemática que consiste en multiplicar ese número por todos los enteros menores que él: **n x (n-1) x (n-2) x ... x 1**. Así, el factorial de 5 (se escribe 5!) vale **5! = 5 x 4 x 3 x 2 x 1 = 120**. Haz un script que calcule el factorial de un número entero.

##### 2.3.4.2 Bucle: for...in

El bucle se ejecuta una vez para cada elemento del array (o propiedad del objeto) y se crea una variable contador que toma como valores la posición del elemento en el array:

```javascript
let datos=[5, 23, 12, 85]
let sumaDatos=0;

for (let indice in datos) {
    sumaDatos += datos[indice];     // los valores que toma indice son 0, 1, 2, 3
}  
// El valor de sumaDatos será 125
```

También sirve para recorrer las propiedades de un objeto:

```javascript
let profe={
    nom:'Juan', 
    ape1='Pla', 
    ape2='Pla'
}
let nombre='';

for (var campo in profe) {
   nombre += profe.campo + ' '; // o profe[campo];
}  
// El valor de nombre será 'Juan Pla Pla '
```

##### 2.3.4.3 Bucle: for...of

Es similar al _for...in_ pero la variable contador en vez de tomar como valor cada índice toma cada elemento. Es nuevo en ES2015:

```javascript
let datos = [5, 23, 12, 85]
let sumaDatos = 0;

for (let valor of datos) {
    sumaDatos += valor;       // los valores que toma valor son 5, 23, 12, 85
}  
// El valor de sumaDatos será 125
```

También sirve para recorrer los caracteres de una cadena de texto:

```javascript
let cadena = 'Hola';

for (let letra of cadena) {
    console.log(letra);     // los valores de letra son 'H', 'o', 'l', 'a'
}  
```

> **EJERCICIO 7_UD1**: Haz 3 funciones a las que se le pasa como parámetro un array de notas y devuelve la nota media. Cada una usará un for de una de las 3 formas vistas. Pruébalas en la consola

### 2.4 Tipos de datos básicos

Para saber de qué tipo es el valor de una variable tenemos el operador **typeof**. Ej.:

* `typeof 3` devuelve _number_
* `typeof 'Hola'` devuelve _string_

En Javascript hay 2 valores especiales:

* **undefined**: es lo que vale una variable a la que no se ha asignado ningún valor
* **null**: es un tipo de valor especial que podemos asignar a una variable. Es como un objeto vacío (`typeof null` devuelve _object_)

También hay otros valores especiales relacionados con operaciones con números:

- **NaN** (_Not a Number_): indica que el resultado de la operación no puede ser convertido a un número (ej. `'Hola'*2`, aunque `'2'*2` daría 4 ya que se convierte la cadena '2' al número 2)
- **Infinity** y **-Infinity**: indica que el resultado es demasiado grande o demasiado pequeño (ej. `1/0` o `-1/0`)

#### 2.4.1 Casting de variables

Como hemos dicho las variables pueden contener cualquier tipo de valor y, en las operaciones, Javascript realiza **automáticamente** las conversiones necesarias para, si es posible, realizar la operación. Por ejemplo:

* `'4' / 2` devuelve 2 (convierte '4' en 4 y realiza la operación)
* `'23' - null` devuelve 0 (hace 23 - 0)
* `'23' - undefined` devuelve _NaN_ (no puede convertir undefined a nada así que no puede hacer la operación)
* `'23' * true` devuelve 23 (23 * 1)
* `'23' * 'Hello'` devuelve _NaN_ (no puede convertir 'Hello')
* `23 + 'Hello'` devuelve '23Hello' (+ es el operador de concatenación así que convierte 23 a '23' y los concatena)
* `23 + '23'` devuelve 2323 (OJO, convierte 23 a '23', no al revés)

Además comentar que en Javascript todo son ojetos por lo que todo tiene métodos y propiedades. Veamos brevemente los tipos de datos básicos.

> **EJERCICIO 8_UD1**: Prueba en la consola las operaciones anteriores y alguna más con la que tengas dudas de qué devolverá

#### 2.4.2 Number

Sólo hay 1 tipo de números, no existen enteros y decimales. El tipo de dato para cualquier número es **number**. El carácter para la coma decimal es el **.** (como en inglés, así que 23,12 debemos escribirlo como 23.12).

Tenemos los operadores aritméticos **+**, **-**, **\***, **/** y **%** y los unarios **++** y **--** y existen los valores especiales **Infinity** y **-Infinity** (`23 / 0` no produce un error sino que devuelve _Infinity_).

Podemos usar los operadores artméticos junto al operador de asignación **=** (+=, -=, *=, /= y %=).

Algunos métodos útiles de los números son:

- **.toFixed(num)**: redondea el número a los decimales indicados. Ej. `23.2376.toFixed(2)` devuelve 23.24
- **.toLocaleString()**: devuelve el número convertido al formato local. Ej. `23.76.toLocaleString()` devuelve '23,76' (convierte el punto decimal en coma)

Podemos forzar la conversión a número con la función **Number(valor)**. Ejemplo `Number('23.12')`devuelve 23.12

Otras funciones útiles son:

- **isNaN(valor)**: nos dice si el valor pasado es un número (false) o no (true)
- **isFinite(valor)**: devuelve _true_ si el valor es finito (no es _Infinity_ ni _-Infinity_). 
- **parseInt(valor)**: convierte el valor pasado a un número entero. Siempre que compience por un número la conversión se podrá hacer. Ej.:

```javascript
parseInt(3.65)      // Devuelve 3
parseInt('3.65')    // Devuelve 3
parseInt('3 manzanas')    // Devuelve 3, Number devolvería NaN
```

- **parseFloat(valor)**: como la anterior pero conserva los decimales

**OJO**: al sumar floats podemos tener problemas:

```javascript
console.log(0.1 + 0.2)    // imprime 0.30000000000000004
```

Para evitarlo redondead los resultados (o `(0.1*10 + 0.2*10) / 10`).

> **EJERCICIO 9_UD1**: Modifica la función que quieras de calcular la nota media para que devuelva la media con 1 decimal

> **EJERCICIO 10_UD1**: Modifica la función que devuelve el cubo de un número para que compruebe si el parámetro pasado es un número entero. Si no es un entero o no es un número mostrará un alert indicando cuál es el problema y devolverá false.

#### 2.4.3 String

Las cadenas de texto van entre comillas simples o dobles, es indiferente. Podemos escapar un caràcter con \ (ej. `'Hola \'Mundo\''` devuelve _Hola 'Mundo'_).

Para forzar la conversión a cadena se usa la función **String(valor)** (ej. `String(23)` devuelve '23')

El operador de concatenación de cadenas es **+**. Ojo porque si pedimos un dato con _prompt_ siempre devuelve una cadena así que si le pedimos la edad al usuario (por ejemplo 20) y se sumamos 10 tendremos 2010 ('20'+10).

Algunos métodos y propiedades de las cadenas son:

* **.length**: devuelve la longitud de una cadena. Ej.: `'Hola mundo'.length` devuelve 10
* **.charAt(posición)**: `'Hola mundo'.charAt(0)` devuelve 'H'
* **.indexOf(carácter)**: `'Hola mundo'.indexOf('o')` devuelve 1. Si no se encuentra devuelve -1
* **.lastIndexOf(carácter)**: `'Hola mundo'.lastIndexOf('o')` devuelve 9
* **.substring(desde, hasta)**: `'Hola mundo'.substring(2,4)` devuelve 'la'
* **.substr(desde, num caracteres)**: `'Hola mundo'.substr(2,4)` devuelve 'la m'
* **.replace(busco, reemplaza)**: `'Hola mundo'.replace('Hola', 'Adiós')` devuelve 'Adiós mundo'
* **.toLocaleLowerCase()**: `'Hola mundo'.toLocaleLowerCase()` devuelve 'hola mundo'
* **.toLocaleUpperCase()**: `'Hola mundo'.toLocaleUpperCase()` devuelve 'HOLA MUNDO'
* **.localeCompare(cadena)**: devuelve -1 si la cadena a que se aplica el método es anterior alfabéticamente a 'cadena', 1 si es posterior y 0 si ambas son iguales. Tiene en cuenta caracteres locales como acentos ñ, ç, etc
* **.trim(cadena)**: `'   Hola mundo   '.trim()` devuelve 'Hola mundo'
* **.startsWith(cadena)**: `'Hola mundo'.startsWith('Hol')` devuelve _true_
* **.endsWith(cadena)**: `'Hola mundo'.endsWith('Hol')` devuelve _false_
* **.includes(cadena)**: `'Hola mundo'.includes('mun')` devuelve _true_
* **.repeat(veces)**: `'Hola mundo'.repeat(3)` devuelve 'Hola mundoHola mundoHola mundo'
* **.split(sepadaror)**: `'Hola mundo'.split(' ')` devuelve el array \['Hola', 'mundo']. `'Hola mundo'.split('')` devuelve el array \['H', 'o', 'l', 'a', ' ', 'm', 'u', 'n', 'd', 'o']

Podemos probar los diferentes métodos en la página de [w3schools](https://www.w3schools.com/jsref/jsref_obj_string.asp).

> **EJERCICIO 11_UD1:** Haz una función a la que se le pasa un DNI (ej. 12345678w o 87654321T) y devolverá si es correcto o no. La letra que debe corresponder a un DNI correcto se obtiene dividiendo la parte numérica entre 23 y cogiendo de la cadena 'TRWAGMYFPDXBNJZSQVHLCKE' la letra correspondiente al resto de la divisón. Por ejemplo, si el resto es 0 la letra será la T y si es 4 será la G. Prueba la función con tu DNI

##### 2.4.3.1 Template literals

Desde ES2015 también podemos poner una cadena entre \` (acento grave) y en ese caso podemos poner dentro variables y expresiones que serán evaluadas al ponerlas dentro de **${}**. También se respetan los saltos de línea, tabuladores, etc que haya dentro. Ejemplo:

```javascript
let edad=25;

console.log(\`El usuario tiene:
${edad} años\`) 
```

Mostrará en la consola:

> El usuario tiene:

> 25 años

#### 2.4.4 Boolean

Los valores booleanos son **true** y **false**. Para convertir algo a booleano se usar **Boolean(valor)** aunque también puede hacerse con la doble negación (**!!**). Cualquier valor se evaluará a _true_ excepto 0, NaN, null, undefined o una cadena vacía ('') que se evaluarán a _false_.

Los operadores lógicos son ! (negación), && (and), \|\| (or).

Para comparar valores tenemos **==** y **===**. La triple igualdad devuelve _true_ si son igual valor y del mismo tipo. Como Javascript hace conversiones de tipos automáticas conviene usar la **===** para evitar cosas como:

* `'3' == 3` true
* `3 == 3.0` true
* `0 == false` true
* `'' == false` true
* `' ' == false` true
* `[] == false` true
* `null == false` false
* `undefined == false` false
* `undefined == null` true

También tenemos 2 operadores de _diferente_: **!=** y **!==** que se comportan como hemos dicho antes.

Los operadores relacionales son >, >=, <, <=. Cuando se compara un número y una cadena ésta se convierte a número y no al revés (`23 > '5'` devuelve _true_, aunque `'23' > '5'` devuelve _false_)  

## 3. Manejo de errores

Si sucede un error en nuestro código el programa dejará de ejecutarse por lo que el usuario tendrá la sensación de que no hace nada (el error sólo se muestra en la consola y el usuario no suele abrirla nunca). Para evitarlo debemos intentar capturar los posibles errores de nuestro código antes de que se produzcan.

En javascript (como en muchos otros lenguajes) el manejo de errores se realiza con sentencias

```javascript
try {
    ...
} 
catch(error) {
    ...
}
```

Dentro del bloque _try_ ponemos el código que queremos proteger y cualquier error producido en él será pasado al bloque _catch_ donde es tratado. Opcionalmente podemos tener al final un bloque _finally_ que se ejecuta tanto si se produce un error como si no. El parámetro que recibe _catch_ es un objeto con las propiedades _name_, que indica el tipo de error (_SyntaxError_, _RangeError_, ... o el genérico _Error_), y _message_, que indica el texto del error producido.

En ocasiones podemos querer que nuestro código genere un error. Esto evita que tengamos que comprobar si el valor devuelto por una función es el adecuado o es un código de error. Por ejemplo tenemos una función para retirar dinero de una cuenta que recibe el saldo de la misma y la cantdad de dinero a retirar y devuelve el nuevo saldo, pero si no hay suficiente saldo no debería restar nada sino mostrar un mensaje al usuario. Sin gestión de errores haríamos:

```javascript
function retirar(saldo, cantidad) {
  if (saldo < cantidad) {
    return false
  }
  return saldo - cantidad
} 

// Y donde se llama a la función_
...
resultado = retirar(saldo, importe)
if (resultado === false
  alert('Saldo insuficiente')
} else {
  saldo = resultado
...
```

Se trata de un código poco claro que podemos mejorar lanzando un error en la función. Para ello se utiliza la instrucción `throw`:

```javascript
  if (saldo < cantidad) {
    throw 'Saldo insuficiente'
  }
```

Por defecto al lanzar un error este será de clase _Error_ pero (el código anterior es equivalente a `throw new Error('Valor no válido')`) aunque podemos lanzarlo de cualquier otra clase (`throw new RangeError('Saldo insuficiente')`) o personalizarlo.

Siempre que vayamos a ejecutar código que pueda generar un error debemos ponerlo dentro de un bloque _try_ por lo que la llamada a la función que contiene el código anterior debería estar dentro de un _try_. El código del ejemplo anterior quedaría:

```javascript
function retirar(saldo, cantidad) {
  if (saldo < cantidad) {
    throw "Saldo insuficiente"
  }
  return saldo - cantidad
} 

// Siempre debemos llamar a esa función desde un bloque _try_
...
try {
  saldo = retirar(saldo, importe)
} catch(err) {
  alert(err)
}
...
```

Podemos ver en detalle cómo funcionan en la página de [MDN web docs](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Sentencias/try...catch) de Mozilla.

## 4. Buenas prácticas

Javascript nos permite hacer muchas cosas que otros lenguajes no nos dejan por lo que debemos ser cuidadosos para no cometer errores de los que no se nos va a avisar.

### 4.1 'use strict'

Si ponemos siempre esta sentencia al principio de nuestro código el intérprete nos avisará si usamos una variale sin declarar (muchas vecees por equivocarnos al escrbir su nombre). En concreto fuerza al navegador a no permitir:

* Usar una variable sin declarar
* Definir más de 1 vez una propiedad de un objeto
* Duplicar un parámetro en una función
* Usar números en octal
* Modificar una propiedad de sólo lectura

### 4.2 Variables

Algunas de las prácticas que deberíamos seguir respecto a las variables son:

* Elegir un buen nombre es fundamental. Evitar abreviaturas o nombres sin significado (a, b, c, ...)
* Evitar en lo posible variables globales
* Usar _let_ para declararlas
* Usar _const_ siempre que una variable no deba cambiar su valor
* Declarar todas las variables al principio
* Inicializar las variables al declararlas
* Evitar conversiones de tipo automáticas
* Usar para nombrarlas la notación _camelCase_

También es conveniente, por motivos de eficiencia no usar objetos Number, String o Boolean sino los tipos primitivos (no usar `let numero = new Number(5)` sino `let numero = 5`) y lo mismo al crear arrays, objetos o expresiones regulares (no usar `let miArray = new Array()` sino `let miArray = []`).

### 4.3 Errores

No se debería estar comprobando lo devuelto por una función para ver si se ha ejecutado correctamente o ha devuelto algún código de error. Si algo es erróneo no debemos devolver un código sino lanzar un error y quien ha llamado a esa función debería hacerlo dentro de un `try...catch` para capturar dicho error. Por ejemplo:

- Mal

```javascript
function muestraDatos(datos) {
   ...
   const nombreMes = getNombreMes(datos.mes);
   if (nombreMes === null) {
       alert('El mes ' + datos.mes + ' es erróneo');
   }
   ...
}

function getNombreMes(mes) {
   mes = mes - 1; // Ajustar el número de mes al índice del array (1 = Ene, 12 = Dic)
   var meses = new Array("Ene", "Feb", "Mar", "Abr", "May", "Jun", "Jul", "Ago", "Sep", "Oct", "Nov", "Dic");
   return meses[mes];
}
```

- Bien

```javascript
function muestraDatos(datos) {
   ...
   try {
      const nombreMes = getNombreMes(datos.mes);
   } catch(err) {
      alert(err)
   }
   ...
}

function getNombreMes(mes) {
   mes = mes - 1; // Ajustar el número de mes al índice del array (1 = Ene, 12 = Dic)
   var meses = new Array("Ene", "Feb", "Mar", "Abr", "May", "Jun", "Jul", "Ago", "Sep", "Oct", "Nov", "Dic");
   if (meses[mes] === null) {
       throw 'El mes ' + mes + ' es erróneo';
   }
   return meses[mes];
}
```

### 4.4 Otras

Algunas reglas más que deberíamos seguir son:

* Debemos ser coherentes a la hora de escribir código: por ejemplo podemos poner (recomendado) o no espacios antes y después del `=` en una asignación pero debemos hacerlo siempre igual. Existen muchas guías de estilo y muy buenas: [Airbnb](https://github.com/airbnb/javascript), [Google](https://google.github.io/styleguide/javascriptguide.xml), [Idiomatic](https://github.com/rwaldron/idiomatic.js), etc. Para obligarnos a seguir las reglas podemos usar alguna herramienta [_linter_](https://www.codereadability.com/what-are-javascript-linters/).
* También es conveniente para mejorar la legibilidad de nuestro código separar las líneas de más de 80 caracteres.
* Usar `===` en las comparaciones
* Si un parámetro puede faltar al llamar a una función darle un valor por defecto
* Y para acabar **comentar el código** cuando sea necesario, pero mejor que sea lo suficientemente claro como para no necesitar comentarios

### 4.5 Clean Code

Estas y otras muchas recomendaciones se recogen el el libro [Clean Code](https://books.google.es/books?id=hjEFCAAAQBAJ&dq=isbn:9780132350884&hl=es&sa=X&ved=0ahUKEwik8cfJwdLpAhURkhQKHcWBAxgQ6AEIJjAA) de _Robert C. Martin_ y en muchos otros libros y articulos. Aquí tenéis un pequeño resumen traducido al castellano:

- [https://github.com/devictoribero/clean-code-javascript](



# Ejercicios Repaso

- [Ejercicios de Repaso UD01](https://despertc.github.io/DWEC-DAW-2324/UD01/Ejercicios/Repaso_UD01.md)



# Bibliografía

* Curso 'Programación con JavaScript'. CEFIRE Xest. Arturo Bernal Mayordomo
* [Curso de JavaScript y TypeScript](https://www.youtube.com/playlist?list=PLiZCpIzKtvqvt4tcQV4SAvaJn7QMdwUbd) de Arturo Bernal en Youtube
* [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/JavaScript). Moz://a. https://developer.mozilla.org/es/docs/Web/JavaScript
* [Introducción a JavaScript](http://librosweb.es/libro/javascript/). Librosweb. http://librosweb.es/libro/javascript/
* [Curso de Javascript (Desarrollo web en entorno cliente)](https://www.youtube.com/playlist?list=PLI7nHlOIIPOJtTDs1HVJABswW-xJcA7_o). Ada Lovecode - Didacticode (90 vídeos)
* [Apuntes Desarrollo Web en Entorno Cliente (DWEC)](https://github.com/sergarb1/ApuntesDWEC). García Barea, Sergi
* [Apuntes Desarrollo Web en Entorno Cliente (DWEC)](https://github.com/cipfpbatoi/materials). Segura Vasco, Juan. CIPFP Batoi.
