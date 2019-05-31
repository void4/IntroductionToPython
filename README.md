# Introduction to programming with the Python language

## Why should I learn programming?
Because you can sense and affect things that are normally out of your reach, compute things faster than you can do on your own. You will be able to build, understand, improve and automate things.

Programming is a superpower!

## Choosing the right language

Python is a great introductory language because how it looks like ("the syntax") is relatively easy to understand and how it works ("the semantics") is intuitive.

Python is great for automating small tasks by interacting with other software and doing art, science and mathematics. Because the language manages the complicated stuff in the background for you, you can write short, but very powerful programs with it.

Writing software for complex systems (like a self-driving car), or in fact anything that needs to be VERY fast or secure, is not Pythons domain, there are much better languages for that.

## Syntax and Semantics

A program consists a text file with a special ending (.py for Python). A program called the interpreter executes the program line by line, starting from the top.

A line can contain a statement or nothing (whitespace or a completely empty line).

When the interpreter encounters an statement it executes it and goes to the next line. Empty lines and everything after a '#' (a comment) are ignored.

A series of lines with the same indentation is called a block. Each statement in the block is executed after the other.

The way the interpreter steps through the program is called the control flow. It's not always one line after the other, a statement may contain another block. In a loop for example, a block can be executed many times.

An expression is replaced by the result of its operation and may have some other side effect (like storing something in memory or printing something on your screen or REALLY printing something).




## Handling data with variables

When you are transforming data, it is often useful to store intermediate values. This allows you to use a computed value many times. The box in which you store a value is somewhere in the working memory of your computer.

You don't have to think about allocating memory when you create a variable or releasing it when you don't need it anymore, Python manages that for you.

The name that refers to the box is called a "variable", because after you created it, you can change the value in the box, or let the name point to another box altogether, so it's variable :)

To read and write data, you need three things:

### The name

The name refers to the box, which has a type and contains a value.

The name can be almost anything, except words that are part of the syntax and therefore have special meaning.
Most programming languages insist on starting with a letter.

You can get the value of a variable by just writing its name, like this:

test

(Imagine the name getting replaced by the value the variable has at this time)

Giving results a name also makes a program more readable, you and other people will understand the program better if they read it later.

### The data type

All programming languages have primitive types, like numbers or character strings.

You write a number like you would on a calculator:

When you create a variable for the first time, you don't have to state the type yourself, Python figures it out for you.

There are also advanced data types, like lists of values.

### The value

This is what's in the box. What it can be is restricted by the data type.

## Syntax

### Addition

Some operators have special meaning, addition, written with '+', like you would on a calculator takes the values on its left and right and adds them.

If both values are numbers, the entire expression is replaced with the result of the operation.

>>>1 + 2
3

'+' is special because it also allows you to put two character strings together, like this:

>>>"Hello" + " " + "world"

The same operator is always evaluated left to right.

When you combine this with other number operators, like '*' (multiplication) or '/' (division), PEMDAS

### Functions

A function is a block of statements with a name.

You can call the function with input values (arguments) and the function can return output values. Any combination is possible, there are functions with an input value but no output value and the other way around. Some have both, some have neither.

In Python, you call a function by writing its name, then a pair of parentheses and within these parens comma separated arguments. Like this:

print("Hello world!")

# Import the power function from the math library
from math import pow
pow(2, 3)
>>>8

When a function is called, the control jumps from the line where it was called to the place where the function was defined. When the function returns a value, the function call is replaced with that value and the expression is evaluated normally.
