# Actividades Repaso UD 04
## Repaso 4.1 - Paso de elementos
Dada la siguiente página web:

```html
<html>
<head>
    <meta charset="utf-8">
    <style>
        body{
            font-family: Verdana, Geneva, Tahoma, sans-serif;
        }
        section{
            display: block;
            float: left;
            width: 40%;
            border: 1px solid #aaaaaa;
            height: 200px;
            overflow-y: auto;
            overflow-x: hidden;
            margin: 10px;   
        }

        h3{
            margin: 0px;
            background: #2196f3;
            width: 100%;
        }

        #contenedor>section>div>p{
            margin: 0px;
        }
 
        #contenedor>section>div>p:hover{
            background: #bbdefb;
            width: 100%;
            cursor: pointer;
        }

    </style>
</head>

<body>
    <div id="contenedor">
        <section>
            <h3>Bloque 1</h3>
            <div>
                <p>item 1</p>
                <p>item 2</p>
                <p>item 3</p>
            </div>
        </section>

        <section>
            <h3>Bloque 2</h3>
            <div>
                <p>item 4</p>
            </div>
        </section>
    </div>
</body>

</html>
```



Se pide añadir una función que se ejecute cuando cargue la página y que dé la siguiente funcionalidad a la misma:

- Cuando hagamos doble click en un item de dentro del bloque, este pasará automáticamente al bloque contrario.
- Deberemos poder hacerlo de forma indefinida, por lo que al crear el elemento y pasarlo al bloque contrario, deberemos añadir el Listener correspondiente otra vez.
