# Actividades Repaso UD 06
## Repaso 6.1 - Petición GET
Dada la siguiente página web:

```html
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <div id="contenido">
          <h1>Ejercicio 6.1 Petición GET</h1>
					<article>
						<div class="imagen">
      						
          	</div>
          </article>
        </div>
        
        <script src="getv1.js"></script>
    </body>
</html>
```

Se pide completar el archivo getv1.js para incluir una imagen random "perros" que se obtendrán a partir del siguiente recurso mediante una petición GET: https://dog.ceo/api/breeds/image/random

Se incluirá la imagen obtenida dentro del div imagen.

El ejercicio se debe realizar de tres formas posibles:

- Promesas
- API Fetch
- async / await

## Repaso 6.2 - Petición POST

Vamos a utilizar el siguiente recurso para simular la introducción de un comentario en una página web: https://jsonplaceholder.typicode.com. En concreto, utilizaremos la dirección para comentarios: https://jsonplaceholder.typicode.com/posts

Los parámetros a enviar en el cuerpo de forma obligatoria son:

| Nombre | Tipo    |
| ------ | ------- |
| title  | string  |
| body   | string  |
| userId | integer |

Para poder probar correctamente este tipo de petición, realizaremos un formulario con el cual interactuaremos y insertaremos el contenido del comentario, el usuario y el post a comentar. Incluiremos un botón de envío que realizará la petición POST. 

Al recibir correctamente el comentario, escribiremos en nuestro DOM un párrafo indicando que se ha introducido correctamente el comentario y el `id` correspondiente que nos devolverá la petición.

Podemos basarnos en la página web utilizada en la actividad anterior.

El ejercicio se debe realizar de tres formas posibles:

- Promesas
- API Fetch
- async / await
