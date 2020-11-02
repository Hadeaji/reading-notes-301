# What is EJS

simply stands for Embedded Javascript.

It is a simple templating language/engine that lets its user create HTML with  javascript.

EJS is mostly useful whenever you have to output HTML with a lot of javascript

Express uses jade as its default template engine

so we would have to tell it to use ejs instead with the following line to your app.js file in the root folder of your project :

`app.set("view engine","ejs");`

> One thing to note is that all files in which ejs syntax are used in must be saved with a .ejs extension

Express also lets us include partials. Imagine setting up a site in which all/some of the pages have the same nav and footer.

With express, all you have to do is to create a sub-directory named partials or whatever name you prefer inside your views directory and put all your modular/shared files there.

`<%include partials/header%>`

`<%include partials/footer%>`

## understanding syntax

While using express, there are 4 major tags that you will need to understand:

- `<% %>` : This is used to embed javascript codes that do return outputs

- `<%= %>` : Used to embed code that is supposed to return and output the result of an expression/computation to the view(page) at run-time.

- `<%- %>` : This takes a string and outputs it’s unescaped value to the view.

- `<%# %>` : Used to include comments in files.

