# NODEJS

## about nodejs

- nodejs is a javascript runtime
- nd turn js to machine code
- with chrome compile engine ==> V8
- nd is C++
- js is single thread and slow
- but nd is fast because of cpp
  -repl

---

integrated terminal ==> ctrl + `

npm init -y ==> initialize project

### package json

these are metadata

```json
{
  "name": "first-project-node",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/hassansaber/first-project-node.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/hassansaber/first-project-node/issues"
  },
  "homepage": "https://github.com/hassansaber/first-project-node#readme"
}
```

---

## Creating server

### HTTP module

[link](https://nodejs.org/api/http.html#http)

```js
const http = require("http");
```

- require == use a module
- every file in nd is a module

#### http module ==>

#### create server method

[link](https://nodejs.org/api/http.html#httpcreateserveroptions-requestlistener)

```js
const server = http.createServer((req, res) => {
  console.log(req);
});
```

#### http module ==>

#### listen method

[link](https://nodejs.org/api/http.html#serverlisten)

```js
server.listen(8000);
```

---

## module global object

- in nd every js file is a module
- in js every variable is accessible with global object of Window

```js
const a = 2;
window.a; // 2
```

with this obj we can import and export between files
[link](https://nodejs.org/api/globals.html#module)
[link](https://nodejs.org/api/modules.html#module)

```js
module.exports = { sayHi };
module.exports = sayHi;
module.exports.greeting = sayHi;
exports = sayHi;
exports.greeting = sayHi;
```

```js
const logger = require("./logger");
const { greeting } = require("./logger"); //new name
const { sayHi } = require("./logger");
```

---

### External module

- we setup them with npm

#### chalk extranal module

make your output pretty in console
[link](https://www.npmjs.com/package/chalk)
