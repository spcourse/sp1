# Water

Implement a program that reports a user's water usage back to them by calculating the how many bottles of drinking water are consumed by the number of minutes they shower.

	How many minutes do you shower? 1
	12
	
	How many minutes do you shower? 10
	120

## Specification

* Create a new file called `water.py` and write a program that asks the user for how long they shower in minutes. Then print the amount of bottles of water that corresponds to that number of minutes. You can assume that one minute of showering takes 12 bottles of water (containing 0.5 Liters each).

* To keep things simple, assume the user always provides a positive integer as input for the amount of minutes. That means you don't have to implement any error handling for the case that a user inputs an invalid value. 

* The result should be identical to the examples given earlier, when provided the same inputs.

## Hints

* This program complies with the common cliches of a standard computer program: it contains an *input*, a *calculation*, and and *output*. Try to represent each of these components in your code!

* Utilize the `input`-function and `int()` to process the input of a user from a string into an integer, to be able to perform calculations with the user-provided values.

* Try to discover the formula that is required for the necessary calculations from the description of the assignment. Finding that formula is the most important part of completing assignments.

## Testing

First, try and run the program yourself with a couple of expected values. You could, for example, provide the values 0, 10 and 137 for the amount of minutes under the shower. If everything seems to be in order, then it's time to make use of `checkpy`. Testing `water` works the same as it did for `hello`, only this time provide `checkpy` with `water` as argument instead. Like this:

	checkpy water

Any unhappy smileys left and you can't figure out what's wrong with your program? Ask for assistance!
