# Actividades Repaso UD 11
## Ejercicio 1 - Funcionalidad completa de la lista
Vamos a terminar con la aplicación de la lista de cosas que hacer dándole la funcionalidad final que tenia la aplicación inicial.

Para ello, creamos el _store_ para el array de cosas a hacer que debe ser accesible desde varios componentes. En él incluimos métodos para añadir un nuevo _todo_, para borrar uno, para cambiar el estado de un _todo_ y para borrarlos todos.

En el componente _todo_list_ debemos incluir el array _todos_ lo que haremos en su data. El resto de componentes no necesitan acceder al array, por lo que no lo incluimos en su data, pero sí llamarán a los métodos para cambiarlo.

Respecto al _todo-item_ debe cambiar los datos tanto al hacer doble click (se borra la tarea) como al marcar/desmarcar el checkbox (se cambia el estado de la tarea).
