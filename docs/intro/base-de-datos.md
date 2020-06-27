# Bases de datos

Para conectarnos a una base de datos debemos instalar las dependencias que corresponden a la base de datos que queremos acceder por ejemplo PostgreSQL, MySQL, MongoDB, etc...

## Dependencias

    $ npm i pg

## Credenciales

Es importante conocer las credenciales para poder acceder a una base de datos en la mayoria de los casos necesitaremos:

- `host`: indica el dominio remoto o local donde se encuntra el servicio de base de datos.
- `port`: puerto donde se encuntra expuesto el servicio
- `user`: nombre del usuario que tiene acceso a la base de datos
- `password`: contraseña secreta del usuario
- `database`: nombre de la base de datos a la que se quiere acceder

Con esas credenciales, tenemos dos opciones para conectarnos a PostgreSQL por medio de node-pg:

## Object conection

`dao/index.js`
```js
const { Client } = require('pg')

// Objeto de conexión
const client = new Client({
  user: 'dbuser',
  host: 'database.server.com',
  database: 'mydb',
  password: 'secretpassword',
  port: 3211,
})

client.connect()
```

### ConectionString

```js
const { Client } = require('pg')
const connectionString =
  'postgres://hello_django:hello_django@0.0.0.0:5433/hello_django_dev'

// String de conexion
const client = new Client({
  connectionString,
  max: 20,
  idleTimeoutMillis: 30000,
  connectionTimeoutMillis: 2000
})

```