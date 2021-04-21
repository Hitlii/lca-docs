# Sprint 2  

## Creacion de propiedades

```js

let property = {
    id: ObjectId(),
    status: 'Venta', // Venta Renta Vendido Oculto 
    type: 'Terreno', // Casa Terreno Rancho,
    zone: 'Campestre', // Campestre Residencial Comercial 
    
    price: 1231232321368000, // Un precio mayor a 150,000 USD debe de mostrar el precio por metro cuadrado, por seguridad
    priceSuffix: 'USD', // En el ordenado y filtrado esto puede ser un problema
    area: 50000, // Poner siempre en metros cuadrados?
    priceSpecial: '400 USD/ha'

    title: 'Venta de terrenos de 4,000 m', 
    description: {
        documents: {
            isDeeded: Boolean // Una propiedad puede tener documentos y no estar escriturada
            text: String, // Puede ser un pedazo de codigo {Quill?}
        },
        services:{
            hasAllServices: Boolean, 
            text: String, // Puede ser un pedazo de codigo
        },
        amenities: String //puede ser un pedazo de codigo
        extras: String //puede ser un pedazo de codigo
        priceArea{
            paymentFacilities: String; // Facilidades de pago, estos se pondria en las cards
            text: [String] // Puede ser un arreglo de pedazos de codigo??
        }
    },
    location:{
        state: 'B.C',
        city: 'Tecate', // Tecate, Mexicali, Ensenada, Tijuana, SanQui
        suburb: 'Loma Tova',
        coordinates: {
            lat: '12.2',
            lng: '20.31'
        }
    },
    media: {
        carrousel: ['/images/tecate/campestre/ZT012.jpg', '....'],
        thumbnail: '/images/tecate/campestre/VT012.jpg',
        area: '/images/tecate/campestre/VT012.jpg',
        video: 'youtube.com/watch?v213212',
    }
}

```




## Client

```js
let Client = {
    _id: ObjectId(),
    name: 'Hydro Flask Camelback',
    genre: 'M', 
    birthday: new Date(1980, 2, 1);
    contact:{
        email:'someEmail@domain.com',
        phone:'somePhone',
    }
    location{
        city: 'Tecate',
        state: 'B.C',
        addres: 'someAddres',
    }
}


```


## Ticket 
```js
let ticket = { // Un ticket resulta de una sola venta o  renta
    _id: ObjectId(),
    type: 'Venta', // Venta Renta
    propertyId: ObjectId(), //

}

```

# Preguntas

* Como filtrar por USD y MXN
    * API De casa cambio para usarla iternamente 
* Como mostrar el precio de propiedad si vale mucha feria
    * Creando un nuevo campo especial para ese tipo de casos 
* Que regresa el quilljs?
* Como ordenar las imagenes de carrousel?
    * Podriamos usar la forma en lo que lo hace instagram ( se ordena segun los campos de texto )
* Como obtener las coordenadas de una zona?
* Como enviar solo la direccion de las imagenes de las propiedades?
   
    * Validators.
    * HandlerMutations.  
    * Apollo Error.
