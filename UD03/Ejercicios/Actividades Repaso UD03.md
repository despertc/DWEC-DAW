# Actividades Repaso UD 03
## Repaso 3.1 - Cadenas de texto
Dada la siguiente página web:

```html
<html>
    <head>
        <meta charset="utf-8"/>
    </head>
<body>
    </body>
    <script>
        // indicamos que al cargar la página se ejecute la función
"cadenas"
        onload=cadenas
        function cadenas(){
            // Pedimos una cadena al usuario
            let cadena=prompt("Escribe una cadena de texto");
            // A completar...
}
    </script>
</html>
```



Se pide completar la función `cadenas` para que muestre en la web mediante la creación de párrafos, información sobre la cadena. Concretamente, queremos saber:

- Si la cadena es en mayúsculas, en minúsculas o es una combinación 
- Qué carácter ocupa la tercera posición
- Cuántos caracteres tiene la cadena
- Posición en la que aparece por primera vez el carácter "a" 
- Posición en la que aparece por última vez el carácter "a"
- Por qué caracter empieza la cadena y por cuá acaba.

Por ejemplo, ante la cadena: "AaeEIioOuU", la salida será:

> ```
> La cadena tiene mayúsculas y minúsculas
> La posición 3 la ocupa el caracter: E
> La cadena tiene 10 caracteres
> El caracter 'a' aparece por primera vez en la posición 1
> El caracter 'a' aparece por última vez en la posición 1
> La cadena empieza por 'A'
> La cadena acaba por 'U'
> ```



## Repaso 3.2 - Modificación DOM

Dada la siguiente página web:

```html
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <div id="contenido">
					<article>
						<h1>Ejercicio 3.2 Repaso</h1>
                <div class="text">
                    <p>Esta es una página web de prueba.</p>
                    <p>En ella practicaremoa con los métodos más básicos de consulta y manipulación del DOM.</p>
                    <p>La página contiene <span id="parrafos">
</span>párrafos</p>
                </div>
          </article>
        </div>
        
        <script>
            onload=modificaDOM;
            function modificaDOM(){
                // Para completar
						}
        </script>
    </body>
</html>
```

Se pide completar la función `modificaDOM`, de forma que formateo la página según los siguientes criterios:

- El elemento con `id="contenido"` tenga un color de fondo #00ffff y un padding de 5px
- Todos los artículos que aparezcan, tendrán un color de fondo #eeeeee,
- Todos los elementos de tipos h1 tengan un color de texto #555555
- Todos los párrafos aparezcan en cursiva.

Además, tendrá que mostrar en el span con `id="parrafos"` la cantidad de párrafos que hay en la página.

## Repaso 3.3 - Cronómetro simple

A partir de un esqueleto HTML básico, realizar un cronometro de X minutos de duración. Los minutos se pedirán por pantalla al usuario antes de arrancar. Solo aceptará valores enteros.

Por ejemplo, si de introduce el valor 5, se abrirá en la página un contador que cuente desde 00:00 hasta 04:59 con una resolución de segundos.

Al terminar el tiempo, el cronómetro parará y se pondrá a 0.
