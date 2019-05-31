# Introduction to programming with the Python language

## Why should I learn programming?
Because you can sense and affect things that are normally out of your reach, compute things faster than you can do on your own. You will be able to build, understand, improve and automate things.

Programming is a superpower!

## Choosing the right language

Each programming language has its tradeoffs.

Python is a great introductory language because how it looks like ("the syntax") is relatively easy to understand and how it works ("the semantics") is intuitive.

It's great for automating small, general tasks by interacting with other software and doing art, science and math. Because the language manages the complicated stuff in the background for you, you can write short, but very powerful programs with it.

Writing software for complex systems (like a self-driving car), or in fact anything that needs to be VERY fast or secure, is not Pythons domain, there are much better languages for that.


## What you will be able to do after this tutorial

The greatest strength of Python is its wealth of libraries

After the general part, I'll show you how you can
- write programs that draw on images
- create a small website

## Syntax and Semantics

The main challenge new programmers encounter is understanding the way the interpreter steps through the program - this is called the control flow. To understand what your program does you need to understand what gets executed when. You need to think a bit like the computer. Luckily, in Python, only one thing is executed at the same time.

What also differentiates programming from writing more simple lists of instructions (like cooking recipes), is that you often want create some effects only when a condition is true, maybe at a specific time, or when the user typed something in. Things like repetition are also common. A process (that is what a running program is called) can have complex behavior.

When you want something to happen, you have to be explicit and specific about it, because the interpreter (unfortunately) does not know what you want. When you want it to stir the pot, you have to tell it exactly how many times, because it won't guess by itself. There is no room for interpretation (hah!).

The specificity can also be a bit frustrating, because a tiny mistake, like forgetting a colon, will result in the program running incorrectly, or not running at all. These errors (called "bugs", because they flew into and block your machine) are sometimes difficult and time-consuming to hunt down. If you are working on a specialized project, you will need to find and understand the right documentation. Patience is key.



top down vs bottom up description

## Interactive mode vs File execution

You can start the interpreter by typing 'python' + Enter in your command line. If you do not give a filename, the interpreter enters the interactive mode, where you can type in programs line by line. You can leave it by typing `exit()` or pressing Ctrl+C.

On the other hand, if you have a program file, you can start execution with:
`python <programname>.py`

A program file consists a text file with a special ending (.py for Python).

Each line can contain a statement or nothing (whitespace or a completely empty line).

A series of lines with the same indentation is called a block. A program called the interpreter executes a block line by line, starting from the top.
When the interpreter encounters an statement it executes it and goes to the next line. Empty lines and everything after a '#' (a comment) are ignored.

It's not always one line after the other, a statement may contain another block. In a loop for example, a block can be executed many times.

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

A function is a block of statements with a name. You can call the function with input values (arguments) and the function can return output values. Any combination is possible, there are functions with an input value but no output value and the other way around. Some have both, some have neither.

#### Calling a function

In Python, you call a function by writing its name, then a pair of parentheses and within these the arguments, separated by a comma. Like this:

print("Hello world!")

When a function is called, the control jumps from the line where it was called to the place where the function was defined. When the function returns a value, the function call is replaced with that value and the expression is evaluated normally.

#### Importing a function

# Import the power function from the math library
from <libraryname> import <object name>

from math import pow
pow(2, 3)
>>>8


#### Defining a function

When the interpreter encounters a function definition, it doesn't execute it, but just remembers its name so you can call it later.

def <functionname>(<arg1Name>, <arg2Name>):
    <firstStatement>
    <secondStatement>
    <etc.>

def square(number):
    squared_number = number * number
    return squared_number

kwargs

## Drawing images

Here we are!

First, we need to install the library that does most of the work for us.

The library is called Pillow and we install it with *pip*, the Python's package manager. After we have installed the library, our programs can use it
from PIL import Image, ImageDraw

In your command line (on Windows: press the windows key and type 'cmd'), type
'pip install Pillow'

You can type this program in line by line in the interpreter
`python`

```python
# Now, we can import it
from PIL import Image

# The Image Library object has two useful functions, Image.new and Image.open:

# Say, we want to create an new image with a width and height of 512 pixels
width = 512
height = 512

# Returns a new image object with a white background
img = Image.new("RGB", (width, height), color="white")

# If you want to draw on top of an existing image:
#   1. put it into the same folder as your program
#   2. use the open function to get an image object
img = Image.open("myImage.png")
# If it isn't in the same folder, just give Image.open the full path to it

# To see the image as it currently is, use
img.show()

# You can also use img.save to store the image in a file
# Be careful not to overwrite any existing file if you don't want that
img.save("outputname.png")

# Now, the Image object in img only lets us get and put single pixels, which is not very useful.
# ImageDraw to the rescue!
from PIL import ImageDraw

draw = ImageDraw.Draw(img)
# *draw* now refers to a Draw object, which lets us draw more complex shapes on the image!

# This draws a line, the first two coordinates are the x and y position of one end,
# the last two the x and y of the other
draw.line([0, 0, 200, 200])

img.show()
# It's a line!

draw.rectangle([20, 20, 40, 400], fill="green", outline="black")

img.show()
# It's the hulk!

# If you want to experiment more, you can explore the documentation here:
# https://pillow.readthedocs.io/en/3.1.x/reference/ImageDraw.html#functions
```

`pip install flask`

# server.py
```python

from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

app.run()
```

Execute this program with
`python server.py`

Now open your browser on
localhost:5000

:)
