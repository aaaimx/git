
# Introducción

Una vez instaladas las herraminetas necesarias (Node.js, VSCode y NPM) podemos empezar a crear nuestro servidor con Node.js.

## Instalar dependencias

NOTA: En algunos sistemas es necesario tener privilegios de superusuario para instalar librerias globales.

**Express Generator**

    $ npm i -g express-generator

**Nodemon**

    $ npm i -g nodemon

## Crear el proyecto

Abrimos una terminal de nuestro sistema, y ejecutamos el siguiente comando:

NOTA: cambie el valor de **nombredelproyecto** por el nombre de su proyecto o use punto (**.**) para indicar que esta dentro de la carpeta raiz.



    $ express --view=hbs --git nombredelproyecto

Ingrese al proyecto desde la terminal, o abra el proyecto en VSCode y use una terminal

    $ cd nombredelproyecto

Instale las dependencias iniciales del proyecto:

    $ npm install

Finalmente, ejecute el proyecto con nodemon para tener un *hot reloading*

    $ nodemon

## Estructura inicial
```
├── app.js
├── bin
│   └── www
├── package.json
├── public
│   ├── images
│   ├── javascripts
│   └── stylesheets
│   └── style.css
├── routes
│   ├── index.js
│   └── users.js
└── views
├── error.hbs
├── index.hbs
└── layout.hbs
```

Los archivos importantes corresponden a `bin/www` que es donde se encuentra el servidor de Node y `app.js` que es la aplicaión de Express y sus respectivas API's de ejemplo.

## Estructura propuesta
Se crean 3 carpetas adicionales: 
- `dao`: que corresponde al Objeto de Acceso de Datos (Data Access Object) aqui ira la conexion y definición de los modelos de Base de datos.

- `controllers`: Controladores individuales del proyecto, aquellas funciones que definiran la conexión, manipulación de la base de datos y lógica de negocio.

- `test`: Pruebas unitarias y de integración del proyecto
```
├── app.js
├── bin
│   └── www
├── controllers
├── dao
├── package.json
├── public
│   ├── images
│   ├── javascripts
│   └── stylesheets
│   └── style.css
├── routes
│   ├── index.js
│   └── users.js
├── test
└── views
├── error.hbs
├── index.hbs
└── layout.hbs
```

### Package.json
El archivo principal de nuestro proyecto que contiene la descripción general del proyecto asi como la relación de dependencias o librerias que utiliza.

NOTA: Todos los proyectos que corren con **Node.js** tienen un `package.json`, asegurese de que exista una carpeta `node_modules` que se crea al ejectutar **npm install**; esa carpeta contiene los archivos de instalación y suele ser muy pesado por lo que no se sube al repositorio (git) y debe estar en el `.gitignore`. Sino existe quiere decir que las dependecias no estan instaladas.
```json
{
  "name": "node-example",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node ./bin/www"
  },
  "dependencies": {
    "cookie-parser": "~1.4.4",
    "debug": "~2.6.9",
    "express": "~4.16.1",
    "hbs": "~4.0.4",
    "http-errors": "~1.6.3",
    "morgan": "~1.9.1"
  }
}
```

## Modulos y buenas practicas ECMASCript 2019

- Usar `const` en vez de `var` donde sea neceario.
- Usar arrow functions `=>` en vez de funciones con scope `function`.
- `module.exports = {}` use la exportación de modules en Node.js para que pueda utilizar, funciones, clases y variables fuera del archivo donde esta declarado.

Más adelante estaremos viendo como cambia el **package.json** a medida que crece el proyecto y se requieren diferentes configuraciones.

## Servidor web y estructura del código

```js
/**
 * Module dependencies.
 */

const app = require('../app');
const debug = require('debug')('node-example:server');
const http = require('http');

/**
 * Get port from environment and store in Express.
 */

const port = normalizePort(process.env.PORT || '3000');
app.set('port', port);

/**
 * Create HTTP server.
 */

const server = http.createServer(app);

/**
 * Listen on provided port, on all network interfaces.
 */

server.listen(port);
server.on('error', onError);
server.on('listening', onListening);

// ...
```

## Express application

```js
const createError = require('http-errors');
const express = require('express');
const path = require('path');
const cookieParser = require('cookie-parser');
const logger = require('morgan');

const indexRouter = require('./routes/index');
const usersRouter = require('./routes/users');

const app = express();

// view engine setup
app.set('views', path.join(\_\_dirname, 'views'));
app.set('view engine', 'hbs');

app.use(logger('dev'));
app.use(express.json());
app.use(express.urlencoded({ extended: false }));
app.use(cookieParser());
app.use(express.static(path.join(\_\_dirname, 'public')));

app.use('/', indexRouter);
app.use('/users', usersRouter);

// ...
```

### Middlewares

El método `.use()` de una aplicaión de Express es utilizada para establecer middlewares los cuales son funciones que son llamdas siempre al inicio de cada petición y que por lo general son utilizadas para modificar o manejar la petición antes de que llegue a la ruta.