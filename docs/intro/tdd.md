# Desarrollo Basado en Pruebas

[TDD](https://es.wikipedia.org/wiki/Desarrollo_guiado_por_pruebas)

## Controladores

```js
function getUsers () {
  return null
}

function getUserById (id) {
  return id
}

module.exports = {
  getUsers,
  getUserById
}
```

## Dependencias

    $ npm i -D mocha chai supertest

```js
const { assert, expect } = require('chai')
const server = require('../bin/www')
const request = require('supertest')(server)
const { getUsers } = require('../controllers/users')

describe('Pruebas para usuarios', () => {
  describe('Checar obtener usuarios ', () => {
    it('Checar funcion getUsers()', async () => {
      const result = await getUsers()
      expect(result).to.be.an('array')
    })
  })
})
```

### Package.json

```json
...
"scripts": {
  "start": "node ./bin/www",
  "test": "./node_modules/.bin/mocha --reporter spec --exit"
},
...
```

### Implementacion

```js
const { client } = require('../dao')

function getUsers () {
  return new Promise(async (resolve, reject) => {
    try {
      await client.connect()
      result = await client.query('SELECT * FROM public.auth_user')
      resolve(result.rows)
    } catch (error) {
      reject(error)
    }
  })
}

function getUserById (id) {
  return new Promise(async (resolve, reject) => {
    try {
      await client.connect()
      result = await client.query(
        `SELECT * FROM public.auth_user WHERE id = ${id} LIMIT 1;`
      )
      resolve(result.rows[0])
    } catch (error) {
      reject(error)
    }
  })
}

module.exports = {
  getUsers,
  getUserById
}
```
