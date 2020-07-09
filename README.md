
# Full Stack skill-test

Hola y bienvenidx a esta prueba de habilidades, en esta ocasión mediremos tus habilidades como desarrolladorx Full Stack creando una API REST para ser utilizada en una "red social" y posteriormente el código-librería que será usado desde el front end para consumir e interactuar con dicha API.

![](https://media0.giphy.com/media/E6jscXfv3AkWQ/giphy.gif)

Los puntos que estaremos evaluando serán:

- Habilidad usando el MERN stack
- Creatividad en el diseño de la REST API
- Capacidad de abstracción para el código librería front end
- Legibilidad del código
- Estructura del proyecto

Sientete libre de resolver tus dudas con nosotros en el intermedio de lo que dure la prueba. Te deseamos suerte y éxito!

## Descripción

### *API REST

Te encontrarás diseñando y construyendo una API REST para una "red social". El proyecto deberá contar sin excepción con dos entidades, PUBLICACIÓN y CATEGORÍA las cuales se describen de la siguiente forma, presta atención a la relación entre ambas entidades:

- PUBLICACIÓN
  - título (string)
  - descripción (string)
  - autor (string)
  - imgUrl (string) // url de la imagen
  - categoría (ObjectID) // relación con la entidad CATEGORÍA

- CATEGORÍA
  - nombre (string)
  - descripción (string)


Esperamos que la API cuente con los siguientes endpoints:

> /posts
> método [GET] (Obtener todos los posts)
>
> /post/:id
> método [GET] (Obtener un post por ID)
>
> /post
> método [POST] (Crear un nuevo post)
>
> /post
> método [DELETE] (Eliminar un post)
>
> /categories
> método [GET] (Obtener todas las categorías)
>
> /category/:id/posts
> método [GET] (Obtener posts por Categoria)
>
> /category
> método [POST] (Crear una nueva categoría)
>
> /category
> método [DELETE] (Eliminar una categoría)
>

### *Adaptador
Una vez llegado este punto vas a construir un adaptador o librería que será utilizado desde el Front End, el cual tendrá capacidad de interactuar con la API para realizar las operaciones CRUD correspondientes. 

Ejemplo:

```javascript
import adapter from '../adapter';

async function __example__() {
    
    // Obtener una categoría
    // adapter.getCategories();
    const categories = await adapter.getCategories(); // << comunica con API REST
    console.log(categories) 
    /*
        result:
        [
            {
                _id: "XXXXYYYYZZZZ",
                name: "Viajes", 
                description: "Categoría para imágenes"
            }, 
            {
                _id: "XXXXYYYYZZZZ",
                name: "Tecnología"
                description: "Categoría para tecnología"
            },
            {...},
            {...},
        ]
    */
    
    
    // Obtener Posts por ID de categoría
    // adapter.getPostsByCategoryID(categoryID: string);
    const posts = await adapter.getPostsByCategory("XXXXYYYYZZZZ"); // << comunica con API REST
    console.log(posts) 
    /*
        result:
        [
            { 
                _id: "XXXXYYYYZZZZ",
                title: "Mi viaje", 
                description: "A la luna!", 
                autor: "Marco", 
                imgUrl: "https://hipertextual.com/files/2015/03/rickroll.jpg",
                category: {
                    _id: "XXXXYYYYZZZZ",
                    name: "Viajes",
                    description: "Categoría para imagenes sobre viajes!"
                }
            },
            {...},
            {...},
        ]
    */
    
    // Registrar un nuevo Post
    // adapter.addPost(name: string, description: string, autor: string, imgUrl: Base64, category: ObjectID);
    const newPost = await adapter.addPost("Nokia 123", "Nuevo smartphone", author: "Diosito", "data:image/png;base64,iVBORw0 ...", "XXXXYYYYZZZZ"); // << comunica con API REST
    console.log(newPost);
    /*
        result:
        { 
            _id: "XXXXYYYYZZZZ",
            title: "Nokia 123", 
            description: "Nuevo smartphone", 
            autor: "Diosito", 
            imgUrl: "https://hipertextual.com/files/2015/03/rickroll.jpg",
            category: {
                _id: "XXXXYYYYZZZZ",
                name: "Tecnología",
                description: "Categoría para tecnología"
            }
        },
    */
    
}
```

Puedes representar las funcionalidades que gustes en el adaptador, sin embargo aquellas que tomaremos en cuenta para la validez de este ejercicio serán:

-  Obtener todas las categorías (por nombre o por ID)
-  Modificar una categoría
-  Eliminar una categoría
-  Obtener todos los post
-  Obtener todos los post (por nombre o por ID de categoría)
-  Añadir un nuevo post
-  Modificar un post
-  Eliminar un post

### *Front End


Para finalizar el ejercicio deberás crear las siguientes pantallas con ReactJS (no es necesario agregar estilos, con la funcionalidad es suficiente), deberán hacer uso del adaptador para conectar con el API:

- Pantalla de Home con lista de categorías
- Pantalla para consulta de todos los posts 
- Pantalla para el registro de un nuevo post

## Reglas

- Máximo de 5 días naturales para la entrega
- La aplicación deberá ser codificada usando las tecnologías descritas anteriormente (NodeJS, MongoDB y React)
- Puedes utilizar Express o Sails para la construcción del API REST
- Puedes utilizar Mongoose para establecer conexión con la base de datos desde NodeJS
- Puedes utilizar React Router DOM para el manejo de rutas en el front end
- El proyecto deberá entregarse en un repositorio con un manual de uso y ejecución

## Recomendaciones

- Has código legible y bien documentado!
- Sé lo más creativo posible!

#### Buena suerte :) 
