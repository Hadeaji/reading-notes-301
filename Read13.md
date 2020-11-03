# Update/Delete

## Client/server architecture

> the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.

![ex](/files/Read13-1.png)

## client side: defining how to send the data

It is done by using the form element when the user fill the data and press on submit.

But to do so the is some setting have to be applied to it first whish are `action` and `method`.

### The action attribute

The `action` attribute defines ***where the data gets sent***.

Its value must be a valid relative or absolute URL.

If this attribute isn't provided, the data will be sent to the the current page.

`<form action="https://example.com">`

### The method attribute

The `method` attribute ***defines how data is sent***.

The most known methods are `GET` and `POST` methods

#### The GET method

Used to get data from the server.

After using it in the form and submitting the data wanted, the id for the first input will appear after the `?` then `=` then the value given after it it will come the `&` then the rest of the inputs ids and values but without the `?`

#### The POST method

It's the method the browser uses to talk to the server

send data and append it or shows results for it on the HTTP

#### Viewing HTTP requests

if you want to see them, you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools

## On the server side: retrieving the data

> Whichever HTTP method you choose, the server receives a string that will be parsed in order to get the data as a list of key/value pairs. The way you access this list depends on the development platform you use and on any specific frameworks you may be using with it.

### A special case: sending files

Sending files with HTML forms is a special case, there are special requirements for handling binary data.

#### The enctype attribute

Because the HTML binary data and HTTP is text protocol The enctype attribute lets you specify the value of the Content-Type.

**If you want to send files, you need to take three extra steps:**

- Set the method attribute to POST because file content can't be put inside URL parameters.

- Set the value of enctype to multipart/form-data because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).

- Include one or more `<input type="file">` controls to allow your users to select the file(s) that will be uploaded.

## Security issues

If you conside Security then sending HTML files is not recommanded At all

the HTML itself is not harmful, but the way the server handles their data makes it unsafe

### Be paranoid: Never trust your users

> All data that comes to your server must be checked and sanitized. Always. No exception.

- **Escape potentially dangerous characters** the charecter that looks like code and feels like it would be excuted

- **Limit the incoming amount of data to allow only what's necessary**

- **Sandbox uploaded files** Upload files on differant server and allow accessing then only from that server

