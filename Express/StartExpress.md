# Server file

### Installing Express
* Create a new project
* Run the following commands on the terminal

```console
$ npm init

$ npm install express --save
```
### Starting a basic Server
* Create a server.js file and add the following code

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req,res)=>{
  res.send('Hello World!')
});
app.listen(port, ()=> {
  console.log(`App running on port ${port}`);
});
```
### Running the App
```console
$ node server.js
      or
$ nodemon (if nodemon already installed)
```
