# HEROKU

## Node.js For Beginners. Deploy Your Blog to Heroku

First of all, we need to create a JavaScript file. Let's name it server.js:

`var http = require("http");`

`http.createServer(function(request, response) {`
  `response.writeHead(200, {"Content-Type": "text/plain"});`
  `response.write("It's alive!");`
  `response.end();`
`}).listen(3000);`

 Run at your terminal:

`node server.js`

Then check it in your browser

### Make it worldwide

Works fine. But it works locally.
WWW is for "World Wide Web" and we will turn your local server into a world wide server.

First step after Heroku installation is to log in to the system from your computer:

`heroku login`

Create your project directory. And then create the server.js file inside of it.

`var http = require("http");`
`var fs = require("fs");`
`var path = require("path");`
`var mime = require("mime");`

Create the package.json file and fill it with proper information.

`{`
  `"name" : "blog",`
  `"version" : "0.0.1",`
  `"description" : "My minimalistic blog",`
  `"dependencies" : {`
    `"mime" : "~1.2.7"`
  `}`
`}`

We will now create send404() function. It will handle the sending of 404 error, which usually appears when requested file doesn't exist:

`function send404(response) {`
  `response.writeHead(404, {"Content-type" : "text/plain"});`
  `response.write("Error 404: resource not found");`
  `response.end();`
`}`

Now we will define sendPage() function. It first writes the header and then sends the contents of the file:

`function sendPage(response, filePath, fileContents) {`
  `response.writeHead(200, {"Content-type" : mime.lookup(path.basename(filePath))});`
  `response.end(fileContents);`
`}`

Notice the way we handle the MIME-types.

Now we'll define how our server will handle responses. This function will return the content of the requested file or the 404 error otherwise:

`function serverWorking(response, absPath) {`
  `fs.exists(absPath, function(exists) {`
    `if (exists) {`
      `fs.readFile(absPath, function(err, data) {`
        `if (err) {`
          `send404(response)`
        `} else {`
          `sendPage(response, absPath, data);`
        `}`
      `});`
    `} else {`
      `send404(response);`
    `}`
  `});`
`}`

And now it's time to create the HTTP server:

`var server = http.createServer(function(request, response) {`
  `var filePath = false;`

  `if (request.url == '/') {`
    `filePath = "public/index.html";`
  `} else {`
    `filePath = "public" + request.url;`
  `}`

  `var absPath = "./" + filePath;`
  `serverWorking(response, absPath);`
`});`

Now we need to start our server.

`http.createServer(<some code here>).listen(3000)`

We can do it when we run our server locally.
But Heroku sets a dynamically assigned port number to your app. That's why we need to handle all this mess with ports as it’s shown below:

`var port_number = server.listen(process.env.PORT || 3000);`

We need to create the index.html file. It will determine our blog's exterior.

Last Step in the **"Heroku: Getting Started with Node"** that we are asked to do

> *View logs and stopping them*

![ex](/files/Read05-1.png)
