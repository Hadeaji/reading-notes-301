# The Call Stack and Debugging

## Definations

> call stack is a mechanism is to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function ,uses the Last In, First Out (LIFO) principle

call stack is a data structure that temporarily store and manage function calls

> n summary, then, we start with an empty Call Stack. Whenever we invoke a function, it is automatically added to the Call Stack. Once the function has executed all of its code, it is automatically removed from the Call Stack. Ultimately, the Stack is empty again.

The call Stack is single and When the functions called and executed one in the time that means that the call stack is synchronous

In Asynchronous JavaScript there will be maybe and event or loop or some functions that tacks too long running

## LIFO:

the last function add is the first to pop up.

Ex:

`function firstFunction(){`
  `throw new Error('Stack Trace Error');`
`}`

`function secondFunction(){`
  `firstFunction();`
`}`

`function thirdFunction(){`
  `secondFunction();`
`}`

`thirdFunction();`

## Temporarily store

As in the previous example the function `secondFunction` stores the value of `firstFunction();` till it returns to it.

it always keep the order of the functions to be executed next and where the values goes 

## What causes a stack overflow?

> A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point.

as soon as the browser reach the maximum stack calls it will send an error instead.

## Types of error messages

- **Reference errors** when you forgot to declare the variable mate. or you declared them after calling them.

- **Syntax errors**  this occurs when you have something that cannot be parsed in terms of syntax

- **Range errors** giving a wrong length for an array or a nigative value 

- **Type errors** trying to us ehelping functions made for data type to another that is not allowing to.

## Debugging

you can use `console.log()` the values you want to check in to know it is value at some point

or you can use the chrome avaliable tools after pressing right click then inspect you choose the source tab

choose the data you want to follow up it allows for much more control.

## Handling errors

there is alot of ways to handle errors but one of them is to use the try and cath method 

in the try you will be executing all the functions in it

in order then it will if all of them ran smoothly without error it will jump over the catch function and ignore all of it's contant.

but if try failed to execute one of it's functions

the JS will run the catch metod with the functions inside and ignore and forget all the values and functions in the try method.

it may be used to show the messege (404 not found) or (sorry somthing went wrong) but is is better than a not working page at all.

## Tools to avoid runtime errors

**quokka** to evaluate your code as you type

**eslint** to make sure your style guide is consistency and it will grab you an error or two along the way
