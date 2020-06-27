# Number Whiz

Let's start out conservatively and write a program that asks the user for two numbers and subsequently calculates the product of those numbers and displays the result on the screen. Like the following example:

	What is the first number? 16
	What is the second number? 4
	64

	What is the first number? 27
	What is the second number? 5
	135

## Specification

* Create a file called `whiz.py` and implement a program that asks the user for two whole numbers, after which the product of those numbers is displayed on the screen via `print`.

## Problem analysis

* This program complies with the common cliches of a standard computer program: it contains an *input*, a *calculation*, and and *output*. Try to represent each of these components in your code!

## Hints

* You only need the Python elements you've learned up until now to correctly implement this program!

* Utilize the `input`-function and `int()` to process the input of a user from a string into an integer, to be able to perform calculations with the user-provided values.

## Testing

First test your program by hand: does it work correctly for all expected input? Start the program by typing the following command in the terminal:

	python whiz.py

Then try the examples at the top of the page. If everything seems to be in order, then it's time to make use of `checkpy`. Testing `whiz` works the same as it did for `hello`, only this time provide `checkpy` with `whiz` as argument instead. Like this:

	checkpy whiz

Any unhappy smileys left and you can't figure out what's wrong with your program? Ask for assistance!
