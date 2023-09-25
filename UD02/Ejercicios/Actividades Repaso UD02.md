# Actividades Repaso UD 02
## Repaso 2.1 - Notas
Vamos a hacer un programa que va pidiendo al usuario que introduzca las notas de un examen y las va guardando en un array. El usuario cada vez puede introducir:
- una sóla nota
- varias separadas por coma (ej. 4.5, 6, 8.75)

Se le continuará pidiendo notas hasta que pulse ‘Cancelar’.

Las notas introducidas se irán almacenando en un array y una vez que estén todas se mostrará por la consola:
- el array con los datos suministrados por el usuario
- el array “limpiado”: quitaremos del array todos los elementos que no sean números o no estén entre 0 y 10
- la nota del 1º suspenso
- el nº total de aprobados y sus notas
- la nota media del examen, redondeada a 2 decimales
- las notas finales: serán cada nota aumentada un 10% por buena actitud y redondeada a un entero

Por ejemplo, si el usuario va introduciendo las siguientes notas: 9, 4.5, 5 , seis, pi, 23, 7, por consola se mostrará:
```
Notas introducidas: 9, 4.5, 5 , seis, pi, 23, 7
Notas válidas: 9, 4.5, 5, 7
El primer suspenso es 4.5
Hay 3 aprobados: 9, 5, 7
La nota media es 6.38
Las notas finales son 10, 5, 6, 8
```

Organizaremos en las siguientes funciones:
- addItems(notas,item): se le pasa el array actual de notas y el nuevo valor introducido por el usuario y devuelve un array con todos los elementos que tenía más los nuevos introducidos, sin modificar.
- clearItems(notas): devuelve el array "limpio" y con sus elementos convertidos a números
- primerSuspenso(notas): devuelve el primer elemento que está suspendido
- aprobados(notas): devuelve un array con sólo los aprobados
- notaMedia(notas): devuelve la media de las notas redondeada a 2 decimales
- cambiaNotas(notas, incremento): devuelve un nuevo array con cada nota incrementada en el porcentaje indicado y redondeada a 2 decimales



**IMPORTANTE**: Utilizaremos **métodos de arrays** en lugar de bucles. No usaremos ningún for para recorrer los arrays. Siempre que sea posible usaremos _Functional Programming_.
