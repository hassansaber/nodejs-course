### JSON global object

[link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)

. `.stringify` ===> obj to json

. `.pars` ===> json to obj

---

### bindings

A binding in JavaScript is the formal terminology for what a lot of people refer to as a variable. In ES2015+, a variable can be defined with the let keyword, but you can also define constant with the const keyword. A binding could refer to either a variable or a constant.

[link](https://stackoverflow.com/questions/49662203/what-does-binding-mean-in-javascript#:~:text=A%20binding%20in%20JavaScript%20is,a%20variable%20or%20a%20constant.)

## same meaning as variables

---

### buffer

[link](https://nodejs.org/api/buffer.html#buffer)

```js
<Buffer 5b 0d 0a 20 20 7b 20 22 69 64
22 3a 20 31 2c 20 22 66 75 6c 6c 6e 61 6d 65 22 3a 20 22 68 61 73 73  61 6e 20 73 61 62 65 72 22 20 7d 2c 0d 0a 20
20 7b ... 89 more bytes>
```

`.toSrting()` ==> buffer to string

#### stream means data s are coming continually from server

buffer is data that is streaming

Buffers in Streams :
Streams work on a concept called buffer. A buffer is a temporary memory that a stream takes to hold some data until it is consumed. In a stream, the buffer size is decided by the highWatermark property on the stream instance which is a number denoting the size of the buffer in bytes.

[link](https://medium.com/developers-arena/streams-and-buffers-in-nodejs-30ff53edd50f#:~:text)

---

### fs module

- read file

```js
const bufferData = fs.readFileSync("./contacts/contacts.json");
const stringData = bufferData.toString();
const dataObject = JSON.parse(stringData);
```

---

### process obj

`console.log(process.argv);`

terminal code:

` node . add="hassan saber"`

```js
[
  "C:\\Program Files\\nodejs\\node.exe",
  "C:\\Users\\Hassan\\Desktop\\proj\\NODEJS\\contact-app-terminal",
  "add=hassan saber",
];
```

---

## yargs package

[link](http://yargs.js.org/)

- same like
  terminal kit [link](https://www.npmjs.com/package/terminal-kit) and command line args [link](https://www.npmjs.com/package/command-line-args)

Yargs

helps you build interactive command line tools, by parsing arguments and generating an elegant user interface.

It gives you:

commands and (grouped) options (my-program.js serve --port=5000).
a dynamically generated help menu based on your arguments:
