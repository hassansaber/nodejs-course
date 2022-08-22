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

---

## npm

- vulnerabilities ==>
  means noghte zaaf
- un ==> remove
- npm list --depth=0 ==> all packages and extra
- npm outdated ==> witch package is old
- extension version lens ===> check version in package json file

---

### nodemon

[link](https://nodemon.io/)

- install it global
- rs ==> restart
- change watching files : nodemon -e html js

---

### script

all of them are in package json

- test
- run

---

### process global object

[link](https://nodejs.org/api/globals.html#process)

- event driven
  ![](data:image/png;base64,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)

- process is an instance of eventemitter class

```js
console.log(process.title); // powershell or npm or..
console.log(process.pid); //process id 1324 ...
console.log(process.arch); //architecture x64
console.log(process.version); // node version
console.log(process.platform); //win 32
console.log(process.env); //environment variables like MOGO_URI
console.log(process.env.NODE_ENV); // future...(production/develop)
console.log(process.exit()); //close application code 0 to 12
//0 == while event loop is empty
//1 == while error
console.log(process.kill(type p id)); //kill process
process.on; //events
process.on('beforeExit',(code)=>console.log('exit code is'+ code)); // example of event
// events are async
//---
console.log(process.argv); // flags
console.log(process.cwd()); // location

```

---

### file system module

[link](https://nodejs.org/api/fs.html#file-system)

### os module

[link](https://nodejs.org/api/os.html#os)

```js
const fs = require("fs");
//fs  orginally is async

fs.writeFile("test.txt", "helllo this is data", (err) => {
  if (err) throw err;
  console.log("data saved");
});
//file name , data , (add option), callback func(runs after everything)

fs.appendFile("test.txt", " \n bye everyone", (err) => {
  if (err) throw err;
  console.log("data added");
}); //append data to file

// fs.writeFileSync().......
// sync no need callback
//and run line by line

fs.rename("test.txt", "greeting.txt", (err) => {
  if (err) throw err;
  console.log("file name changed");
});

fs.unlink("greeting.txt", (err) => {
  if (err) throw err;
  console.log("file deleted");
}); // delete file
```

```js
const os = require("os");

console.log(os.platform()); //win 32
console.log(os.arch()); // x64
console.log(os.userInfo());
//{
//  uid: -1,
//  gid: -1,
//  username: 'Hassan',
//  homedir: 'C:\\Users\\Hassan',
//  shell: null
//}

console.log(os.release()); //10.0.4849
console.log(os.hostname()); //DESKTOP-P4PKUPT
console.log(os.uptime()); //32584 mil sec system is on
```

---
