# Leap year

Implement a program called `leap.py` that prints all the leap years between a `first_year` (inclusive) and a `last_year` (exclusive). In the [Gregorian calendar](https://en.wikipedia.org/wiki/Leap_year#Gregorian_calendar), leap years are years that are divisible by 4, but not by 100. Except when divisible 400, in which case it is also a leap year.

Example 1:

	Which is the first year? 2090
	Which is the last year? 2120
	2092
	2096
	2104
	2108
	2112
	2116

Example 2:

	Which is the first year? 1990
	Which is the last year? 2020
	1992
	1996
	2000
	2004
	2008
	2012
	2016

## Specification

* Ask the user to provide two years.

* You may assume the user inputs valid integer numbers (and not words or decimal numbers). But make sure that the second year is bigger than the first. If not, ask the user to input the second year again. (A `while` loop could be useful here.)

* Print all the leap years between the first and the second year. The first year is included, the second isn't. Print every leap year on a new line.

* Make sure that your program does not output anything other leap years.

## Problem analysis

An important programming skill is problem decomposition. Break a complex problem up into simpler sub-problems.

Take a couple of minutes of time, before any coding, to draw the problem with **pen and paper**. Illustrate how you would take on this problem and how you would divide the problem into smaller and simpler steps.

For this assignment we'll help you with the decomposition and guide you through some of the steps required to find the final solution.

## Step 1: check leap year

The core problem to solve is to determine if a year is a leap year. So let's focus on that first. Write some code to ask the user to input a year:

	year = input("Which is the first year? ")
	year = int(year)

Now write some code to determine if the user has entered a leap year. If the user would enter 1996, the following statement should be printed:

	1996 is a leap year.

If the user enters 1997:

	1997 is not a leap year.

Start simple: only test if the year is divisible by 4, forget about divisibility by 100 and 400, for now. Tip: You can use the modulo operator (`%`) to test for divisibility. For example the program below will test if 9 is divisible by 3 (which, of course, is the case):

	x = 9
	if x % 3 == 0:
	    print(f'{x} is divisible by 3')

Once this works, add the extra checks for divisibility by 100 and 400. If you did it correctly you should find that 1996 and 2000 are leap years, but 2100 isn't.

## Step 2: check a sequence of years

Now we can add some complexity. Take the code from before and ask the user for a second year. You may assume for now that the second year that the user enters is bigger than the first year. Now print for every year between the first and last year if it is a leap year or not.

Like so:
	Which is the first year? 1900
	Which is the last year? 1910
	1900 is not a leap year.
	1901 is not a leap year.
	1902 is not a leap year.
	1903 is not a leap year.
	1904 is a leap year.
	1905 is not a leap year.
	1906 is not a leap year.
	1907 is not a leap year.
	1908 is a leap year.
	1909 is not a leap year.

Create a `for`-loop to do this. Why not a `while`-loop? If you're not sure about the answer, discuss with someone.

## Step 3: validate user input

In the previous step we assumed for now that the second year that the user enters was bigger than the first year. This might not be the case.

Validate the user input: If the second year the uses enters is not strictly greater than the first year, ask again. Keep asking until the user enters a year that is bigger than the first year.

This can best be solved using a `while`-loop. Why not a `for`-loop. Again, if you're not sure, discuss this with someone.

## Step 4: finishing touches

Almost there. We just need to clean up the output now. It should only print the years, no text, and it should only do so for the leap years. When there is no leap year, nothing should be printed.

Now, carefully read the specification at the top of the assignment and make sure your program works exactly as specified.

## Hints

* You only need the Python elements you've learned up until now to correctly implement this program!

## Testing

To be sure to test your program using `checkpy`:

	checkpy leap
