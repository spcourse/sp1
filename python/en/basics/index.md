# Basic Elements

A **program** is a sequence of instructions that specify how a manipulation should occur. Such a manipulation can be mathematical in nature, like solving a set of equations, or finding the roots of a polynomial. But it can also be a symbolic manipulation, such as finding and replacing text in a document.

Though the specifics can differ, there is only a limited number of **instructions** present in each programming language:

information input (input)
: Receiving data from the keyboard, data file or other external source such as the internet.

information output (output)
: Displaying data on the computer screen, writing data to a file or other ways of retaining data.

calculating
: Performing basic mathematical manipulations such as adding or multiplying.

conditional execution
: Verifying whether a condition is dependent on verification to perform specific actions.

repetition
: Repeating a single task or set of tasks multiple times, often times with variation between repetitions.

And believe it or not, but that's about all you'll be needing. Every program you've ever used on the computer, no matter how complicated, at the core consists out of some nature of these action. **Programming** can be seen as repeatedly decomposing a large, complex task in to smaller, easier subtasks, until you can **implement** a program in a programming language, using only the above 5 elements.

Here you'll find some of these elements in the way that you can use them in Python. Using these elements will help you implement the solution for the very first assignment shortly.

## Printing

After writing a program you can then execute it (*running* it). The computer then reads your code, line for line, and executes any instructions it encounters.

Make a text file **exercise.py** (remember how?) and add the following lines to it:

    print("Hello, world!")
    print("Hee, hello there.")
    print("Making quick progress.")
    print("Funny")
    print('Hey, does this still print?')
    print("Ivo's computer does not work today.")
    print('He said: "Hello."')

> Practicing for this course can be done by literally copying examples word for word. Don't use the *copy-paste* function though, because that way you don't make any mistakes and you'll learn less. Type out all examples you see and fix your mistakes if you get an error message!

Now start the program you've just carefully copied, word for word:

    python exercise.py

What's the result? Did you make any mistakes? Any errors? And did you see that the quotation marks are sometimes different (single and double)? The sequence of characters that you type after `print` has to be started and ended by quotation marks (of the same kind!). Such a sequence is called a **string**.

We can also print multiple times on the same line. By default `print` adds an **ENTER** each time you use it, so that the following `print` statement continues on a new line. But you can manually prevent that **ENTER** from being added:

    print("The temperature is", end=" ")
    print(8, end=" ")
    print("degrees Celsius")

That way the entire message is printed on a single line. Try it for yourself!

This can also be achieved by adding multiple values to a single print statement:

    print("The temperature is", 8, "degrees Celsius")

See how each value (argument) is separated by a comma?

## Calculations

Next, add the following lines to your `exercise.py`:

    print(1)
    print(1 + 1)
    print(1 + 1 + 1)
    print(3 + 2)
    print(8)
    print(5 + 8 + 8 - 8)
    print("5 + 8 + 8 - 8")

You can also perform basic math. The *result* of the calculation is displayed on the screen. Except the last line: that one shows the formula (*expression*) between parentheses. Just like earlier with the texts. The expression within the brackets is a string and not a formula that can readily be calculated.

> Do you get an error message if you run the program? Chances are that you've made a mistake copying the commands leaving Python confused what you meant in the first place. Take a close look to find where you've made that mistake. If you can't seem to find it, do ask for some assistance. Learning to understand error messages is an important part of this course. That's why we want you to make a mistake every now and then!

## Operators

Below you'll find a list of mathematical operators you can use to compose formulas.

| operator | explanation               |
| -------- | ------------------------- |
| `1 + 2`  | addition                  |
| `2 - 1`  | subtraction               |
| `1 * 2`  | multiplication            |
| `2 / 1`  | division                  |
| `2 % 1`  | modulo (remainder)        |
| `2 ** 1` | exponentiation            |


Note: when two whole numbers are divided by using two `/`-operator, the result will always be a whole number. SO `3//2` won't be `1.5` but `1`. That is why the `%`-operator fits in so nicely; it gives the remainder after division.

## Variables

A **value** is one of the core components of any program. In the examples above, you've seen sequences of characters and also numbers. Up until now we've only worked with **constant values** that are set whilst writing the actual program (for example the text `"Hello, world!"`). Though if we'd already know all values when implementing our programs, we would not need computers at all! Let's take full advantage of a computer's strength: calculating.

To be able to use results (values) from one calculation in another calculation we have to temporarily store these results. As a solution Python offers you to assign names to values. These name-value pairs are called **variables**. By using the `=` operator we can combine a name and a value, and consequently use that value elsewhere.

In Dutch:

![embed](https://player.vimeo.com/video/287248523)

In English, read more about [variables and values](http://greenteapress.com/thinkpython/html/thinkpython003.html) at Think Python.

## Types

There exist a couple of different kinds of values in Python; we call them **types**. In the following table you can see three of the most important ones:

| example         | type  |                                                          |
| ----------------- | ----- | -------------------------------------------------------- |
| `'Hello, World!'` | str   | a sequence of characters: a **string**                        |
| `'3.2'`           | str   | once again a **string**, because of the quotation marks       |
| `17`              | int   | a whole number: an **integer**                       |
| `3.2`             | float | a decimal: a **float**, known as a floating point number |

You can also **convert** types from one into the other. For instance you could use `int()` to cast a value into an integer. But only if at all possible, else Python will start complaining:

| conversion                 | result                                                      |
| ------------------------- | -------------------------------------------------------------- |
| `print(int('32'))`        | `32`                                                           |
| `print(int('Hello'))`     | `ValueError: invalid literal for int(): Hello`                 |
| `print(int(3.99999))`     | `3` (Note! no error, but there is information loss) |
| `print(int(-2.3))`        | `-2`                                                           |
| `print(float(32))`        | `32.0`                                                         |
| `print(float('3.14159'))` | `3.14159`                                                      |
| `print(str(32))`          | `'32'`                                                         |
| `print(str(3.14159))`     | `'3.14159'`                                                    |

Did you notice that decimals are denoted in the American Style (with a point instead of a comma)? This is the case for most programming languages.

## User input

Besides having your program printing to the user, you can also ask for input from the user. This way you can write **interactive programs** that can perform calculations based on user provided values. Python comes with a variety of different function to prompt for input. One of which is `input()`, which can be used as shown below:

    name = input("Please enter your first name: ")
    print("Hello,", name)


The string `"Please enter your first name: "` that follows the function `input`, is immediately displayed on the users screen when `input` is executed. After which `input` will patiently wait for the user to fill in any value and until they press **enter**. The provided value is now assigned a name. In the example above it is coincidentally assigned the name `name`. After which it is printed on the next line using the variable `name` within the print statement.

The `input` function always gives you the user provided value as a string. But sometimes you might want the user to provide a number, so you can perform a calculation. Then you'd have to use one of the conversions demonstrated above. For instance:

    seat_count = input("How many seats should be reserved?")
    seat_count = int(seat_count)

## Format

We've already demonstrated how to print variables in a string. For example:

    temperature = 1000
    print("The temperature is", temperature, "degrees.")

There is also another, better, way of printing variables in a string:

    print(f"The temperature is {temperature} degrees.")

The `f` that precedes the quotation marks of the string denotes that this is a **formatted string**. In which the accolades, `{}`, signify a placeholder that contains a variable. Upon printing the part of the string in accolades is replaced for the the value that variable has at the time of printing.

This is especially useful when printing multiple variables:

    temperature = 1000
    pressure = 1.013
    print(f"It is {temperature} degrees and the air pressure is {pressure} bar.")

You can also perform arithmetic or other actions within the curly braces `{}`, though that is often times better done ahead of printing.

## Comments

If a single file contains a sizable amount of Python-code, it is good practice to clearly denote *what is where* (for the reader of the code, not the user of the program). To that end you can add lines of commentary to your code. They look like this:

    # calculation
    x = x + 1

or

    # output
    print(x)

With a hashtag (`#`) you tell Python that it does not have to execute that line of code, but it is instead a comment. It is common practice to write a comment *above* the block of code it refers to.  By adding comments to your code, the code is easier to understand for you and possibly other people that use your code. 

Aside from a comment about small blocks of code throughout your program, it is also useful to describe the use of a program at the top of the file. For **exercise.py** the following **header comment** would suffice:

    # Exercise with Python Module 1
    # M. Stegeman
    # 24-8-2018

Now add comments to your file. Each time explaining a component of your program with a short descriptive text.
