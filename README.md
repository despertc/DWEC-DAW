# DESENVOLUPAMENT WEB ENTORN CLIENT 23-24

Apuntes del módulo de "Desarrollo Web en Entorno Cliente" del 2º curso del CFGS "Desarrollo de Aplicaciones Web" para el curso 2023-2024.

## Bloques

El módulo se va a dividir en 2 grandes bloques:

1. **Javascript:** En la primera evaluación aprenderemos a usar el lenguaje Javascipt repasando lo visto en primer curso y estableciendo las bases para el framework Vue.
2. **Vue**: En este segundo bloque usaremos el framework Javascript **Vue JS**

## Licencia

[![Licencia de Creative Commons](https://camo.githubusercontent.com/f05d4039b67688cfdf339d2a445ad686a60551f9891734c418f7096184de5fac/68747470733a2f2f692e6372656174697665636f6d6d6f6e732e6f72672f6c2f62792d6e632d73612f342e302f38387833312e706e67)](http://creativecommons.org/licenses/by-nc-sa/4.0/)
Este obra está bajo una [licencia de Creative Commons Reconocimiento-NoComercial-CompartirIgual 4.0 Internacional](http://creativecommons.org/licenses/by-nc-sa/4.0/).

Todos los apuntes de este módulo se comparten bajo esta licencia.

## Entorno de trabajo

### Visual Studio Code

Descargamos el paquete **.deb** de la página de [Visual Studio Code](https://code.visualstudio.com/Download) y lo instalamos.

Posteriormente instalaremos diferentes extensiones como **[Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)** para poder trabajar con ficheros *vue* que usaremos en el siguiente bloque de Vue.

Debemos tener la **terminal** integrada en Visual Studio Code. En caso contrario, será necesario que instalemos esta extensión.

### Google Chrome

Utilizaremos este navegador para ejecutar nuestas aplicaciones y nuestras pruebas con JS y Vue. Lo podemos descargar de [aquí](https://www.google.com.mx/intl/es-419/chrome/?brand=CHBD&gclid=Cj0KCQiAtrnuBRDXARIsABiN-7AAMm13Ae3KDIib46Laxfe6tzD_w4yvDdpq5XsPw1eNlOkZ_0-3x3IaAvLEEALw_wcB&gclsrc=aw.ds).

Instalaremos también de forma recomandada las siguientes extensiones:

- [Vue DevTools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd?hl=en)
- [Json Viewer Awesome](https://chrome.google.com/webstore/detail/json-viewer-pro/eifflpmocdbdmepbjaopkkhbfmdgijcc)

### npm

Es el gestor de paquetes de **Node JS**. Si no lo tenemos instalaremos node.js tal y como se indica en la página de [nodejs.org](https://nodejs.org/es/download/package-manager/). Para comprobar la versión utilizamos:

```
node --version
```

### Proyecto base JS

Una vez instalado npm y todo lo necesario de VS Code, vamos a trabajar con un proyecto realizado con Vue para poder hacer pruebas con JS directamente y de una forma cómoda.

Lo primero que debemos de hacer después de descargar el código es ejecutar el comando:

```
npm install
```

Ese comando descargará todos los módulos de node necesarios para ejecutar el proyecto.

Cuando termine de instalar los node_modules, entonces podermos ejecutar el proyecto de con el siguiente comando

```
npm start
```

Para que eso funcione, recuerden que deben de ejecutar ese comando en el mismo directorio donde se encuentra el `package.json`

### Vue CLI

Aunque Vue CLI no se utilizará hasta el segundo bloque, vamos a instalarlo ahora al principio del curso para posteriormente no tener problemas. Seguiremos la guía publicada en su [página oficial](https://cli.vuejs.org/guide/installation.html).

## Guía didáctica

### 1. Introducción

Este módulo pertenece al segundo curso del C.F.G.S. Desarrollo de Aplicaciones Web. Al módulo le corresponden un total de 140 horas, que se imparten a razón de 7 horas en la semana.

El objetivo final del módulo es que el alumno adquiera conocimientos sobre la programación de páginas web dinámicas que se ejecutan en el cliente.

Este módulo está íntimamente relacionado con el de **Desarrollo Web en Entorno Servidor** y el de **Diseño de Interfaces Web**.

### 2. Conocimientos previos

Para poder empezar el módulo con garantías son necesarios los siguientes conocimientos previos:

- Creación de programas utilizando lenguajes de programación
- Creación de páginas web con HTML
- Aplicación de diseño a páginas web con CSS

### 3. Objetivos

El objetivo del módulo es que los alumnos adquieran los conocimientos necesarios sobre la programación de aplicaciones web que se ejecutan en el cliente.

Los objetivos del módulo expresados como *resultados de aprendizaje* son:

- Selecciona las arquitecturas y tecnologías de programación sobre clientes Web, identificando y analizando las capacidades y características de cada una.
- Escribe sentencias simples, aplicando la sintaxis del lenguaje y verificando su ejecución sobre navegadores Web
- Escribe código, identificando y aplicando las funcionalidades aportadas por los objetos predefinidos del lenguaje.
- Programa código para clientes Web analizando y utilizando estructuras definidas por el usuario.
- Desarrolla aplicaciones Web interactivas integrante mecanismos de manejo de acontecimientos.
- Desarrolla aplicaciones web analizando y aplicando las características del modelo de objetos del documento.
- Desarrolla aplicaciones Web dinámicas, reconociendo y aplicando mecanismos de comunicación asíncrona entre cliente y servidor.

### 4. Contenidos

Los contenidos básicos de este módulo son:

- Selección de arquitecturas y herramientas de programación:
  - Modelos de programación en entornos cliente/servidor.
  - Mecanismos de ejecución de código en un navegador web.
  - Capacidades y limitaciones de ejecución.
  - Compatibilidad con navegadores web.
  - Características de los lenguajes script.
  - Lenguajes de programación en entorno cliente.
  - Tecnologías y lenguajes asociados.
  - Integración del código con los hashtags en documentos HTML.
  - Herramientas de programación.
  - Navegadores. Tipo y características.
  - Especificaciones oficiales (DOM, CSS, XHTML, EcmaScript, entre otros).
- Manejo de la sintaxis del lenguaje:
  - Hashtags y ubicación del código.
  - Variables. Tipo y ámbito.
  - Tipo de datos.
  - Conversiones entre tipos de datos.
  - Literales.
  - Asignaciones.
  - Operadores. Precedencia de los operadores.
  - Expresiones.
  - Comentarios al código.
  - Órdenes.
  - Bloques de código.
  - Decisiones.
  - Bucles.
  - Arquitectura cliente/servidor.
  - Estructuras de control de flujo.
  - Convenciones de formato y codificación.
  - Herramientas de depuración de errores.
- Utilización de los objetos predefinidos del lenguaje:
  - Utilización de objetos. Objetos nativos del lenguaje.
  - Interacción con el navegador. Objetos predefinidos asociados.
  - Generación de texto y elementos HTML das de código. Manipulación de elementos HTML dinámicamente.
  - Gestión y creación de macros.
  - Marcos imbricados.
  - Ejecución de código entre macros.
  - Aplicaciones prácticas de las macros.
  - Gestión de la apariencia de la ventana.
  - Creación de ventanas nuevas. Comunicación entre ventanas.
- Programación con arrays, funciones y objetos definidos por el usuario:
  - Funciones predefinidas del lenguaje.
  - Llamamientos a funciones. Definición de funciones.
  - Arrays
  - Inicialización de *arrays
  - Recorrido de *arrays
  - Creación de objetos.
  - Definición de métodos y propiedades.
- Interacción con el usuario: acontecimientos y formularios:
  - Modelo de gestión de acontecimientos.
  - Modelo de acontecimientos estándares.
  - Controladores de acontecimientos.
  - Utilización de formularios desde código.
  - Acceso a los miembros del formulario.
  - Modificación de apariencia y comportamiento.
  - Validación y envío de formularios.
  - Expresiones regulares.
  - Utilización de galletas.
  - Escritura y lectura de galletas.
  - Uso de frameworks. Desarrollo rápido de aplicaciones.
- Utilización del modelo de objetos del documento (DOM):
  - El modelo de objetos del documento (DOM).
  - Objetos del modelo. Propiedades y métodos de los objetos.
  - Representación de la página web como una estructura en árbol.
  - Acceso al documento desde código.
  - Creación y modificación de elementos.
  - El modelo de acontecimientos.
  - Programación de acontecimientos.
  - Diferencias en las implementaciones del modelo.
  - Desarrollo de aplicaciones multicliente.
- Utilización de mecanismos de comunicación asíncrona:
  - Mecanismos de comunicación asíncrona.
  - Objetos, propiedades y métodos relacionados.
  - Recuperación remota de información.
  - Programación de aplicaciones con comunicación asíncrona.
  - Modificación dinámica del documento utilizando comunicación asíncrona.
  - Formatos para el envío y la recepción de información.
  - Librerías de actualización dinámica.
  - Ventajas e inconvenientes del uso de la comunicación asíncrona.

Todos estos contenidos se organizan en 2 bloques temáticos:

- Bloque 1: JavaScript
- Bloque 2: Frameworks JavaScript. Vue JS

Además, al final del módulo y de forma optativa, se realizará un proyecto integrador junto con los módulos de *Desarrollo Web en Entorno Servidor* y *Interfaces Web* (si hay disponibilidad).

Los contenidos detallados de cada bloque son:

- Bloque 1: JavaScript
  - UD1 - Introducción y sintaxis del lenguaje.
  - UD2 - Arrays y objetos.
  - UD3 - DOM y BOM.
  - UD4 - Eventos
  - UD5 - Objetos nativos y formularios
  - UD6 - Ajax y promesas.
  - UD7 - Apis y otros usos.
  - UD8 - Testeo con JS.
- Bloque 2: Vue JS
  - UD9 - Introducción y elementos básicos. Directivas
  - UD10 - Componentes
  - UD11 - Comunicación entre componentes
  - UD12 - Axios 
  - UD13 - SPA: vue-router
  - UD14 - Otros elementos a estudiar. Composition API.

### 5. Metodología

La metodología de impartición del módulo será una mínima exposición teórica de contenidos y mucho trabajo en clase y en casa de prácticas, ejercicios y ejemplos para facilitar la comprensión.

La manera de trabajar en clase la parte práctica será programar de forma infividual.

La idea es dedicar el tiempo de clase a practicar y programar y los conceptos más teóricos verlos en casa para aclarar después en clase las dudas que puedan surgir.

Para comprobar que se han entendido los conceptos teóricos se harán cuestionarios después de cada tema. Además se realizarán diferentes ejercicios y prácticas.

Al final de cada bloque temático se realizará un examen principalmente práctico.

### 6. Temporalitzación

Aquesta temporalització és una previsió i pot modificar-se per les circumstàncies que puguen ocórrer:

- 1ª Evaluación
  - Bloque 1 - JavaScript
  - Bloque 2 - Vue JS: UD09 a UD11
- 2ª Evaluación
  - Bloque 2 - Vue JS: UD12 a UD14
  - Proyecto intermódulos SCRUM
- 3ª Evaluación -----> Plan de recuperación para la evaluación extraordinaria.

### 7. Criterios de evaluación y calificación

Los criterios de calificación utilizados son:

- La nota final del módulo será la media ponderada de los 2 bloques y el proyecto integrador según los siguientes porcentajes:

  - Bloque 1: 50% (>=5)
  - Bloque 2: 50% (>=5)
  - Proyecto: + 20% (>=5)

- La nota de cada bloque será:

  - Cuestionarios, Ejercicios y prácticas evaluables: 40% (>=5)

  - Examen del bloque 60% (>=5)


Para aprobar cada bloque es necesario obtener al menos un 5 tanto en la parte de ejercicios como en el examen.

Para aprobar el módulo hay que tener aprobados los 2 bloques.

#### 7.1 Recuperaciones

Para recuperar la parte práctica de cada bloque el alumno tendrá que entregar las prácticas no aprobadas y/o alguna práctica de recuperación (según indicación del profesor).

Para recuperar el examen de un bloque se hará un examen de recuperación antes de la evaluación ordinaria de febrero.

Quien no tenga aprobado todo el módulo en la evaluación ordinaria se tendrá que examinar de TODO el curso en la evaluación extraordinaria y tendrá que hacer unas prácticas de recuperación.

Para recuperar el proyecto integrador se tendrá que realizar de nuevo el proyecto o hacer un nuevo proyecto (según valoro el profesor) antes de la evaluación extraordinaria. En caso de tener el resto del módulo aprobado se guardará la nota hasta entonces.

#### 7.2 Calificación de los ejercicios

Los ejercicios se irán corrigiendo en clase, preguntando de forma individual y con la siguiente escala de notas:

- No realizado: no se ha hecho el ejercicio. Nota: 0
- No Apto: el ejercicio no funciona o no cibre los mínimos pedidos. Nota: 2,5
- Apto: el programa funciona pero el código es de poca calidad. Nota: 5
- Apto+: el programa funciona y el código es correcto, está correctamente comentado, se controlan los posibles errores y en general se utilizan los elementos y herramientas adecuadas para solucionar el problema. Nota: 7,5
- Apto++: se ha mejorado o ampliado el programa propuesto y el código es eficiente y difícilmente mejorable. Nota: 10