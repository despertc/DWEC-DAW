# Actividades Repaso UD 10


## Ejercicio 1 - Lista de tareas con componentes

Vamos a seguir con la aplicación de la lista de cosas que hacer pero dividiéndola en componentes.

La decisión de qué componentes crear es subjetiva pero en principio cuanto más descompongamos más posibilidades tendremos de reutilizar componentes. Nosotros haremos los siguientes componentes:

* TodoList: muestra la lista de tareas a realizar. Dentro tendrá:
  * todo-item: cada una de las tareas a hacer
* AddItem: incluye el formulario para añadir una nueva tarea (el input y el botón)
* DelAll: el botón para borrar toda la lista

Transformaremos la aplicacación en SFC utilizando Vue-cli. Simplemente crearemos un fichero para cada uno de estos componentes. Nuestro anterior _index.html_ será el \<template> del componente principal **App.vue**, que en un sección <script> deberá importar y registrar cada uno de los componentes usados en el _template_ en forma de etiqueta y mediante kebab-case (<todo-list> , <todo-add> y <del-all> ). Lo mismo haremos dentro de TodoList, importando y utilizando la etiqueta <todo-item> . 

**Pasos que se deben realizar**:

1. Crear el componente que mostrará la lista: *TodoList*
   - Su _template_ es un div que incluye el título (que será una variable para poderlo reutilizar) y la lista con las tareas a mostrar. Cada una de ellas será un subcomponente llamado _todo-item_
   - Como parámetro recibirá el título de la lista como hemos indicado antes llama al subcomponente _todo-item_ para cada tarea (v-for) y le pasa la tarea que debe mostrar
   - Sus datos será el array de tareas
   - Los métodos los dejamos tal cual aunque ahora no funcionan porque nadie los llama.
1. Crear el componente al que llama el anterior: _TodoItem_
   - Recibirá un objeto con la tarea a mostrar
   - Su template será el <li> que tenía en el HTML pero quitando el _v-for_ porque él sólo se encarga de mostrar 1 item
   - El método para borrarlo al hacer doble click ya no puede funcionar porque el componente no tiene acceso al array de tareas. De momento sólo ponemos un _alert_ que nos diga que lo queremos borrar
1. Crear el componente: *AddItem*
   - Su _template_ será el <input> y el <button> que teníamos en el HTML, pero como sólo puede haber un elemento en el template los incluimos dentro de un <div>
   - No recibe ningún parámetro pero sí tiene una variable propia, _newTodo_, que quitamos del componente principal para añadirla a este componente
   - El método de añadir tarea ya no funcionará porque no tenemos acceso al array de tareas así que de momento mostraremos un _alert_ con lo que queremos añadir.
1. Creo el componente *DelAll*
   - Su _template_ es el botón
   - Ni recibe parámetros ni tiene variables propias
   - Con el método pasa lo mismo que en los otros casos así que simplemente muestro un _alert_

