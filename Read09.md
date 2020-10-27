# Refactoring

## What is functional programming?

> Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — **Wikipedia**

### **Pure functions**

**It returns the same result if given the same arguments**

A pure function must give the same result every time it is called and in order to do so it has to:

1. not use external variables because they might change and the result will be differant
2. using the rendom number means that it will give differant results everytime
3. It should not change on global variables instead of having the function changing the var value you can call it as a parameter and make the new value for the function it self instead.

### Pure functions benefits

> It is always a pain to think about all the possibilities and have to modify that specific function to meet all of them but because of pure functioning you dont have to worry about what's not going to happen.

We don’t need to think of situations when the same parameter has different results — because it will never happen.

### Immutability

when you have static variabiles that you have to modify or change but you cant then don't.

Just recreate them in the function and get the new value that you wanted.

### Referential transparency

> ***{pure functions + immutable data = referential transparency}***

### Functions as first-class entities

functions are also treated as values and used as data.

it can be refer to, pass it as a parameter and return it as result.

### Higher-order functions

we mean a function that either:

- takes one or more functions as arguments, or returns a function as its result.

### Filter

using the boolen values to get the answers like when you want to push some numbers that apply the statment, when the callback function indecate true it will push the value.

### Map

> The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

the whole idea in to new values instead of changing

the function .map() will make it much easier for you as you can easily return new array with the new values in it without changing the old one

### Reduce

> The idea of reduce is to receive a function and a collection, and return a value created by combining the items.

you can use the `Reduce` in the proper way in order to make the fuction as your value



## Strategies

- Return early from functions instead if writing multi empty lines for a return.

- Cache variables so functions can be read like sentences better naming and more profissional.

- Check for Web APIs before implementing your own functionality and ending up wasting a lot of time and effort.
