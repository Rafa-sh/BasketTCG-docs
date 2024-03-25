---
title: Markdown
icon: fontawesome/brands/markdown
---

## Metadatos

Al principio del archivo markdown,
hay una cabecera con metadatos, en esta documentación se usan principalmente title, para el título, e icon, para el icono  

Por ejemplo, aquí el inicio de esta página en markdown
```md
---
title: Markdown
icon: fontawesome/brands/markdown
---

## Metadatos

Al principio del archivo markdownm
```

### title
title contiene el título de la página.
```md
---
title: Markdown
---
```
### icon
icon contiene el icono de la página.

Puedes buscar los iconos [aquí](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#search)

Por ejemplo, `:simple-postgresql:` sería `icon: simple/postgresql` como icono para la página

## Documento

### Nueva linea
Para introducir una nueva linea, es necesario poner 2 espacios al final de la linea  

Si tienes algún problema de que el texto esta juntandose, es probablemente la razón

### Títulos

Puedes poner Títulos usando `#`,
```md
# Título 1, reservado
## Título 2
### Título 3
#### Título 4
##### Título 5
###### Título 6
```
#### Ejemplo título 4
##### Ejemplo título 5
###### Ejemplo título 6

### Negrita e italica

```md
*Texto en italica*
**Texto en negrita**
*** Texto en italica y negrita***
```
*Texto en italica*  
**Texto en negrita**  
*** Texto en italica y negrita***  

### Citación
```md
> Ejemplo de citación
```
> Ejemplo de citación

### Listas
#### Lista ordenada
Las listas ordenadas se ordenan automáticamente, simplemente hay que poner un número, seguido de un punto y un espacio
```md
1. Primer elemento
    1. Primer subelemento
        1. Primer sub-subelemento
            1. Primer sub-sub-subelemento
1. Segundo elemento
1. Tercer elemento
```

1. Primer elemento
    1. Primer subelemento
        1. Primer sub-subelemento
            1. Primer sub-sub-subelemento
1. Segundo elemento
1. Tercer elemento

#### Lista desordenada
Se puede usar `['-', '+', '*']` independientemente
```md
- Primer elemento
    * Primer subelemento
* Segundo elemento
+ Tercer elemento
```

- Primer elemento
    * Primer subelemento
* Segundo elemento
+ Tercer elemento

### Código
Puedes insertar código, y la libreria pygments se encargará automáticamente de usar el syntax highlighting adecuado, ademas, mkdocs añadirá varias funciones a los bloques de código.

Para insertar un bloque de código, usamos 3 comillas:
```
 ```bash
 # Esto es código de ejemplo
 echo "codigo de ejemplo"
 ```
```
Resultado:
```bash
 # Esto es código de ejemplo
 echo "codigo de ejemplo"
```

Para insertar un título al bloque de código (normalmente, el nombre del archivo), podemos poner `title="nombre"`

A continuación habrán ejemplos de bloques de código de cada lenguaje usado en el proyecto. Pero si lo desea, para ver todos los lenguajes soportados por la libreria, puedes investigar [aquí](https://pygments.org/docs/lexers/)

```
 ```bash title="ejemplo.sh"
 # Esto es código de ejemplo
 echo "codigo de ejemplo"
 ```
```
Resultado:
```bash title="ejemplo.sh"
 # Esto es código de ejemplo
 echo "codigo de ejemplo"
```

#### SQL (PostgreSQL)
Hay soporte para SQL como el dialecto de SQL de PostgreSQL.

Puedes usar `postgresql`, y `postgres`
```postgres title="scripts/script.sql"
DO $$
BEGIN
    -- Check if all tables exist
    IF EXISTS (
        SELECT 1 FROM information_schema.tables
        WHERE table_name = 'usuarios'
```

#### PHP
puedes usar php, php3, php4, y php5

Es necesario añadir `<?php` al principio
```php title="backend/app/Http/Controllers/CartasController.php"
<?php
 // devolver carta por id
    public function GetCarta($id){
        $card = Cartas::find($id); // con esto hago un select * from cartas where id = $id
        
        if($card){
            return $card;
        }

        return response()->json(['error' => 'Carta no encontrada'], 404); // con esto devuelvo un json con un mensaje de error y un codigo 404
    }
```

#### JS
Hay soporte tanto para js como JSX (React).
Ya que el frontend usa React, es MUY recomendable usar react en vez de js para los bloques de código, aquí un ejemplo:

##### Con JS
puedes usar `javascript`, y `js`
```js title="frontend/src/App.js"
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```
##### Con JSX (React)
O puedes usar `jsx`, y `react`
```react title="frontend/src/App.js"
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;const myElement = <h1>I Love JSX!</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

#### CSS
puedes usar `css`
```css title="frontend/src/index.css"
code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}
```

#### HTML
puedes usar `html`
```html title="frontend/public/index.html"
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" /><div>
```

#### Docker
Para docker usamos tanto Dockrfile, como docker-compose.
docker-compose es un archivo yaml, por tanto hay que usar "yaml" para archivos docker-compose

##### Dockerfile
Puedes usar docker, y dockerfile
```docker title="backend/Dockerfile"
FROM php:8.2-apache

# Configuration
RUN echo 'memory_limit = 512M' >> /usr/local/etc/php/conf.d/docker-php-memlimit.ini;
```
##### docker-compose.yml
Puedes usar yaml
```yaml title="docker-compose.yml"
  db:
    image: postgres
    env_file: .env
    volumes:
      - ./data/pg_data:/var/lib/postgresql/data
    ports:
      - 5433:5432
```
### Lineas horizontales
Puedes crear lineas horizontales poniendo una linea con solo 3 o más asteriscos (***), guiones (---) o  guiones bajos (___)
```md
---
___
***
```
---
___
***

### Enlaces e Imágenes
Para insertar enlaces o imagénes, usamos corchetes `[]` Para el nombre del enlace o imagen, y a continuación parentesis `()` para el propio enlace.

Por último, en caso de ser una imagen, ponemos una exclamación al principio
```md
[Enlace a esta página](https://rafa-sh.github.io/BasketTCG-docs/Referencia/markdown/)  
![Logo](../assets/logo.png)
```
[Enlace a esta página](https://rafa-sh.github.io/BasketTCG-docs/Referencia/markdown/)  
![Logo](../assets/logo.png)

#### Manipular imágenes
Para manipular una imagen, podemos usar html básico. Por desgracia markdown solo sopota manipualr imágenes de esta forma.
```html
<img src="https://rafa-sh.github.io/BasketTCG-docs/assets/logo.png" style="
    width: 100px;
    display: block;
    margin-left: auto;
    margin-right: auto;
">
```
<img src="https://rafa-sh.github.io/BasketTCG-docs/assets/logo.png" style="
    width: 200px;
    display: block;
    margin-left: auto;
    margin-right: auto;
">

### Tablas
Puedes usar tres o mas guiones `---` y tuberias `|` para crear tablas. Aunque es recomndable usar algún generador de tablas markdown como [este](https://www.tablesgenerator.com/markdown_tables)
```md
Es necesaria una linea vacia encima y debajo de la tabla

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

#### Alinear texto en una tabla
```
Es necesaria una linea vacia encima y debajo de la tabla

| Syntax      | Description |  
| ----------- | ----------- |  
| Header      | Title       |  
| Paragraph   | Text        |  

#### Alinear texto en una tabla
poniendo dos puntos `:` puedes señalar si quieres alinear el texto de una tabla a la izquierda, derecha, o centro

```md

| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```

| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

### HTML
Puedes usar etiquetas HTML libremente, aunque no son necesarias excepto para manipular imágenes  
  
```md
Esta <b>palabra</b> usa HTML su enfasis, **esta** no.
```
Esta <b>palabra</b> usa HTML su enfasis, **esta** no.  

Poder usar HTML nos permite poder insertar casi cualquir cosa, como un video de youtube

```html
<iframe src="https://www.youtube-nocookie.com/embed/GtL1huin9EE" allowfullscreen style="
    width: 960px;
    height: 540px;
    display: block;
    margin-left: auto;
    margin-right: auto;"></iframe>
```

<iframe src="https://www.youtube-nocookie.com/embed/njX2bu-_Vw4" allowfullscreen style="
    width: 960px;
    height: 540px;
    display: block;
    margin-left: auto;
    margin-right: auto;"></iframe>
