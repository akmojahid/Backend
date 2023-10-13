# 💚 What is Backend ?

## 💙 Internet
➔ Like i have smartphone and i am sending "hii" msg to anyone then what happend here ?? <br/>
➔ it converts into *data packets* which are invisible for human and they go to the nearest tower / ISP <br/>
➔ Then tower receive data packets and convert them into *electrical signals*  <br/>
➔ these electrical signals goes to any other country through *optical fibers* through ocean <br/>
➔ then the same electrical signals goes to Tower in other country then converted into data packets <br/>
➔ data packets received by user <br/>

<br/>
➔ for small area , sended HII msg that converted into packets then it goes to tower / ISP ( internet service provider like JIO,AIRTEL,VI ) then same process as above <br/>
<br/>


➔ this ecosystem known as Internet [ more info chatGpt](https://chat.openai.com/share/86e0c5f3-9882-4b13-b7c4-6552d4afefce)

## 🧡 IP address and Mac address
➔ mobile has ip address and mac address <br/>
➔ but when we connect with router at that time it uses Mac address <br/>

## 💛 Server
➔ A server is a computer or a software system that provides services, resources, or functionality to other computers or programs, often referred to as clients.  <br/>
➔ if any computer is connected with internet and it programmed to accept Request and it can give Response.  <br/>
➔ computer + programmed + connects with internet = server  <br/>
➔ Client-server architecture = client jo request send karta hai and Server jo response bhejta hai <br/>
➔ Serverroom has just many CPUs <br/>

## ❤️ http and https
➔ hyper text transfer protocol / secured <br/>
➔ protocol hai jiske basis par internet surf karne ki aazadi milti hai - data ka aana jaana iski wajah se ho raha hai <br/>
➔ if any web has HTTP means not secured then the packages sended by the device can be seen by anyone by using hacking devices because data is not encrypted <br/>
➔ HTTPS data packages are also captured by anyone but the data are encrypted so there is no meaning of this <br/>

## 💜 Ports 
➔ server par commumication k liye port hote hai - port par server listen karta hai <br/>
➔ ports are just numbers <br/>
➔ [chatGpt](https://chat.openai.com/share/c674fb10-b527-46ef-9d8a-1429e97c6620) <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 🧡 server create using Express.js
➔ create folder then go into this folder using terminal <br/>
➔ `npm init` or `npm init -y` to create package.json file <br/>
➔ `npm i express` to create nodeModule file <br/>
➔ then create `server.js` file

```
// 📂 server.js

// 1) server instantiate
const express = require('express');
const app = express();

// 2) server live

app.listen(3000, ()=>{
    console.log("server started at port number 3000");
})

// here 3000 is port number from where our server can do communication or listen

```

➔ Routes

```
const bodyParser = require('body-parser');   // used to parese req.body in express -> PUT or POST
app.use(bodyParser.json() );   // specifically parse JSON data & add it to the request.Body object

// here "/" is route

app.get('/',(request,response)=>{
    response.send("Hello jee, kaise ho");
})


app.post('/api/cars', (request,response)=>{
    const {name, brand} = request.body;
    console.log(name);
    console.log(brand);
    response.send("car submitted successfully");
})

```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💛 MONGOOSE

➔ connects mongoDB database and expressJs server using MONGOOSE ( ODM library - object document model )  <br/>
➔ in expressJs server data treats as object and in mongo data treat as document  <br/>
➔ `npm i mongoose` install

```
const mongoose = require('mongoose');
mongoose.connect('mongodb://127.0.0.1:27017/testDb',{
    useNewurlParser : true,
    useUnifiedTopology : true
})
.then(()=>{console.log("connection successfull between express server with mongoDB")})
.catch(()=>{console.log("error")})


// here testDb is db name that we have created in the mongodb compass
```

### 🔥 Make automatic run using NODEMON
➔ [chatgpt](https://chat.openai.com/share/91fa8e2e-63aa-4f63-a0da-38b50898e9ea)

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

# 🌈 Chapter 1 - Introduction to Node, NPM, Package.JSON

## 💛 What is NODE ?
➔ runtime + apis  <br/>
➔ runtime environment for Js + apis <br/>  ➔ asynchronous <br/> 
➔ non blocking I/O  <br/>  <br/>
 
➔ Is it web-server? -- No but you can make it using ExpressJs   <br/>
➔ Why Node is used in webserver? -- Heavy I/O + small code footprint  <br/>

## 🧡 Module System in node
➔ Running any JavaScript file from node using `node filename.js`  <br/>
➔ Modules are basic containers or functions in Node/JavaScript system. 1 file can be one module in Javascript.<br/>

➔ export 
```
// 📂 module.js

function sum (a,b){
    return a + b ;
}

exports.sum = sum ;

//----------------------------
// other way

exports.sum = (a,b) =>{
    return a + b ;
}



// "exports" ek type ka module he hai like OBJECT
// and "exports.sum" kar ke hum export ke andar sum ki property bana rahe hai
// and then "=sum" means uske andar sum function ko rakh rahe hai
```
<br/>
 
➔ import 
```
// 📂 index.js

const module = require("./module");  // way of import 

console.log(module);    // OP => { sum: [Function: sum] }

console.log(module.sum(4,5)); // OP => 9
```

➔ [Es6 type import export](https://chat.openai.com/share/796432e7-43ce-4ca8-aa4a-710d3e98cff8)

## 💜 NPM 
➔ create folder then go into this folder using terminal <br/>
➔ `npm init` or `npm init -y` to create package.json file ( is a configuration file for node projects which has scripts, dependencies, devDependencies etc ) <br/>
<br/>
➔ if there is not package.json file available then you cannot use `npm install anything` to install any online modules available for node on NPM repository online. <br/>
➔ `npm i express` to add express and nodeModule files <br/>
➔ after doing this you can see express version in "package.json" file in *dependencies* <br/>
<br/>
🔥 **Dev dependancy** - ye sirf development time k liye hai -- ye server k main code se realted nhii hai <br/>
➔ ex. NODEMON is a package for running node server and track live changes to re-start again. <br/>
➔ `npm install nodemon --save-dev` installation of devdependency therefore --save-dev <br/>
```
// 📂 package.json
...

  "scripts": {
    "start": "nodemon index.js",
    "dev": "nodemon index.js"
  },

// here index.js means mainFileName.js

...
```
➔ `scripts` inside package.json can be used like `npm run <script-name>` e.g `npm run dev`. Only for `npm start` you can avoid run.<br/>
<br/>

➔ use `npm install -g nodemon` to install packages globally ( --global or -g ) on your system. Not just in the project but useful all over your system.<br/>
➔ How to uninstall packages like `npm un <package-name>` or `npm uninstall <package-name>`  <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
<br/>

# 🌈 Chapter 2 - Server Concepts with Node - http module

## 🧡 Client server
<img src="https://media.licdn.com/dms/image/C5112AQFLhgv0KmXgWQ/article-cover_image-shrink_720_1280/0/1564214969082?e=2147483647&v=beta&t=GGVxl-frWfy6mwFBC9kAkZJIr5-S0A1Fy1mpNKjP784" width="600px" height="300px" />

➔ *here client send REQUEST(req) to the server and server gives RESPONSE(res)* <br/>
➔ *but server can only understand HTTP protocol as language* <br/>

🔥 **HTTP requests**  <br/>
➔ Type of Request :: GET, POST, PUT, DELETE etc.  <br/>
➔ Headers :: Meta data sent by your browser like browser name, cookies, authentication information etc.  <br/>
➔ Query Parameters (url?`name=john`) :: This is used in GET requests to send data to server  <br/>
➔ Route Params (url/`john`)  <br/>
➔ Body data :: This is used in POST and other requests to send data to server  <br/>

🔥 **HTTP responses** <br/>
➔ Response status code :: (200, 404, 403, 502) here `2XX - success`, `3XX - redirections`, `4XX - client error`, `5XX - server error`  <br/>
➔ Response body :: Actual data to be sent to client : HTML, JS, JSON, CSS, Image etc. <br/>
➔ Headers :: Meta data sent by your server back to client like server name, content size, last updated time etc. <br/>

## ❤️ Create a simple HTTP server using the built-in http module in NodeJs
➔ [code with explaination](https://chat.openai.com/share/1eccb9c7-ac43-46d8-a36c-e14ac52e9413) <br/>

➔ what is  [`res.setHeader(name,value)` ](https://chat.openai.com/share/27826b3e-3e1a-486a-a140-8dcf735af393) <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
<br/>

# 🌈 Chapter 3 - Express JS
➔ ExpressJS is de-facto Node framework - and used in most Node applications which are used as web server.<br/>
➔ You can install express `npm install express` <br/>
<br/>

## 🧡 about FS [what is filesystem](https://chat.openai.com/share/edfba47e-cb29-4e8b-9c79-9b692d895cde) <br/>

```
const fs = require('fs');

const index = fs.readFileSync('anyFile.`xtension`', 'utf-8');
console.log('File contents:', index);

// ==== OR ====

try {
  const index = fs.readFileSync('anyFile.`xtension`', 'utf-8');
  console.log('File contents:', index);
} catch (error) {
  console.error('Error reading the file:', error);
}

```
## 💜 create expres server [chatGpt](https://chat.openai.com/share/2a18d381-58b8-4c64-9d77-71d5e01b3f03) 

```
const express = require("express");
const server = express();

server.listen(3030,()=>{
  console.log("server start on 3030 port");
});
```

➔ Response methods (res is our response objects)
```
server.get('/demo', (req, res) => {

    //res.send('Hello, Express as simple msg');     //  res.send()===> for sending html or txt

    //res.send("<h1>hello in html</h1>");           //  res.send()===> for sending html or txt

    //res.sendFile("/Usera/parth/desktop/03-express-js/index.html");      //  res.sendFile() ==> for sending File

    //res.json(product);       // res.json ==> for sending JSON

    //res.sendStatus(404);     // res.sendStatus(xxx) - for sending HTTP status only

    res.send("hello with status")     // sending multiple ( file + statusCode )
      .status(200); 
});


// res.send we can see on our webpage with url "/"
```


## 💛 HTTP Request Types we generally use 
➔ API / Endpoints / Routes are used inter-changeably but they are related to server paths. <br/>
```
server.get("/",(req, res)=>{
  res.json({type:"GET"});
})

server.post("/",(req, res)=>{
  res.json({type:"POST"});
})

server.put("/",(req, res)=>{
  res.json({type:"PUT"});
})

server.delete("/",(req, res)=>{
  res.json({type:"DELETE"});
})

server.patch("/",(req, res)=>{
  res.json({type:"PATCH"});
})
```
## 💚 Middleware
➔ Middleware - Modifies the request before it reaches the next middleware or endpoints. <br/>
➔ Sequence of middleware is very important, as first middleware is first traversed by request. <br/>

➔ [chatGpt read first](https://chat.openai.com/share/d11b014d-1463-49ca-bb13-750e3e5bfaae) <br/>

1️⃣ Application level : server.use(middleware)
```
server.use((req, res, next) => {
  console.log('Middleware function executed.');
  next();
});
```

2️⃣ Router level : server.get('/', middleware, (req,res)=>{})
```
const middleware = (req,res,next) =>{
    // all conditions here
    if(condition){
        res.send("authorized");
        next();
    }
    else{
        res.send("unauthorized").status(400); 
    }
}

server.get('/', middleware, (req,res)=>{})

//==== OR =====

const router = express.Router();

// Router-level middleware
router.use((req, res, next) => {
  console.log('This middleware is executed for routes defined on this router.');
  next();
});

// Route definition with router-level middleware
router.get('/', (req, res) => {
  res.send('Response for the root route.');
});
```

3️⃣ Built-in middleware - [chatGpt](https://chat.openai.com/share/eb5d170e-b0da-4e3f-9c11-f5a7d38fb295)
```
// Built-in middleware for JSON parsing and for parsing body data
server.use(express.json());

// for static hosting
server.use(express.static('public'));
```

4️⃣ External Middle-wares / third party (ex. Morgon )
```
// npm i morgan

const morgan = require('morgan');
server.use(morgan('dev'));   // here "dev" is predefined-method like 
```
