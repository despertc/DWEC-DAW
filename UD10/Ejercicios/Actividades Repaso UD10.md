# Actividades Repaso UD 10
## Ejercicio 1 - Lista de tareas con componentes
Vamos a seguir con la aplicación de la lista de cosas que hacer pero dividiéndola en componentes.

La decisión de qué componentes crear es subjetiva pero en principio cuanto más descompongamos más posibilidades tendremos de reutilizar componentes. Nosotros haremos los siguientes componentes:

* todo-list: muestra la lista de tareas a realizar. Dentro tendrá:
  * todo-item: cada una de las tareas a hacer
* add-item: incluye el formulario para añadir una nueva tarea (el input y el botón)
* del-all: el botón para borrar toda la lista

**Pasos que se deben realizar**:

1. Crear el componente que mostrará la lista: _todo-list_.
   - Su _template_ es un div que incluye el título (que será una variable para poderlo reutilizar) y la lista con las tareas a mostrar. Cada una de ellas será un subcomponente llamado _todo-item_
   - Como parámetro recibirá el título de la lista como hemos indicado antes
   - Llama al subcomponente _todo-item_ para cada tarea (v-for) y le pasa la tarea que debe mostrar
   - Sus datos será el array de tareas
   - Los métodos los dejamos tal cual aunque ahora no funcionan porque nadie los llama.
1. Crear el componente al que llama el anterior, _todo-item_. 
   - Recibirá un objeto con la tarea a mostrar
   - Su template será el <li> que tenía en el HTML pero quitando el _v-for_ porque él sólo se encarga de mostrar 1 item
   - El método para borrarlo al hacer doble click ya no puede funcionar porque el componente no tiene acceso al array de tareas. De momento sólo ponemos un _alert_ que nos diga que lo queremos borrar
1. Crear el componente _add-item_.
   - Su _template_ será el \<input> y el \<button> que teníamos en el HTML, pero como sólo puede haber un elemento en el template los incluimos dentro de un <div>
   - No recibe ningún parámetro pero sí tiene una variable propia, _newTodo_, que quitamos del componente principal para añadirla a este componente
   - El método addTodo ya no funciona porque no tengo acceso al array de tareas así que de momento muestro un _alert_ con lo que querría añadir
1. Creo el componente _del-all_
   - Su _template_ es el botón
   - Ni recibe parámetros ni tiene variables propias
   - Con el método pasa lo mismo que en los otros casos así que simplemente muestro un _alert_

## Ejercicio 2 - Componentes en SFC

Recordemos que la aplicación que estamos desarrollando tiene los componentes:

- todo-list: lista de tareas a hacer. Cada item de la lista es un componente _todo-item_
- todo-item: cada elemento de la lista de tareas a hacer
- todo-add: formulario para añadir una nueva tarea
- todo-del-all: botón para eliminar todas las tareas

Para transformar esto en SFC simplemente crearemos un fichero para cada uno de estos componentes. Nuestro anterior _index.html_ será el \<template> del componente principal **App.vue**, que en un sección \<script> deberá importar y registrar cada uno de los componentes usados en el _template_ (_todo-list_, _todo-add_ y _todo-del-all_).
