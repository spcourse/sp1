# Functions

A *function* is a piece of code that is assigned a name, so you can reuse it multiple times throughout your code. A function you've used before for instance is `len()`, to calculate the length of a list. But also think of functions such as `arange()`, `plot()` and others.

You can also define functions yourself. If, for example, you've written a piece of code to plot your data, you wouldn't want to copy all that code each time you acquire new data.

Functions are an important aspect of learning how to code. The start of a function is denoted by the word `def`, which is followed by the function name (which you can choose for yourself), and subsequently the parentheses `()` which may or may not contain any parameters. Closed finally by a colon `:`. Check out the example:

    def print_greeting():
        print("Hello")

Note that much like with `if`-statements and `for`-loops, all code that is indented is part of the functions **code block**. Thus you can terminate a function by simply *unindenting* any following code that you write.

This is a function that `print`s the string `Hello` to the terminal. If you add the aforementioned *definition* to a Python file, your computer will know that a function with the name `print_greeting()` exists. But the function hasn't yet been *executed*! You have to do so manually, by explicitly *calling* the function. This is how:

    print_greeting()

## Examples of declaring functions 

![embed](https://vimeo.com/album/5380760/embed)

## Style and design

Using functions improves readability of your code. With a well-chosen name for each function you can easily gain an overview of what the code is meant to do as a whole. It allows you to first quickly read all function names of a program before having to try and comprehend the functional code.

Functions can also be expedient when you repeatedly have to use a more or less identical piece of code. Often times when you catch yourself copy pasting parts of your own code, you can better spend some time to find a way to efficiently reuse the code your copying by defining a function!
