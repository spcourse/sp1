# Leap birthday

People that are born on February 29 are called leap-year babies. Leap-year babies only have an actual birthday on leap years. Born on any other date it easy to compute when you can celebrate your $$k$$'th birthday. Not so for leap-year babies.

Implement a program called `birthday.py` that asks the user for a number $$k$$ and compute the *k'th birthday of a leap-year baby born on February 29 2000*.

Example 1:

	Enter a number: 1
	Birthday #1 is in the year 2004

Example 2:

	Enter a number: 2
	Birthday #2 is in the year 2008

Example 3:

	Enter a number: 1000
	Birthday #1000 is in the year 6124

## Specification

* Ask the user to provide a positive number. If the number is not positive ask again.

* Print the $$k$$'th leap year starting from 2000 (so 2000 is the 0th, and 2004 is the 1st year).

### Constraints
Just as before: Python has a lot of built-in tricks to make your life as a programmer easier. But, before you start
using those tricks it is important to be fully comfortable with the basics. So for this
exercise there are some constraints on what you're allowed to use.

* You are only allowed to use the concepts that are discussed in this module.
For an overview of those concepts have a look [here](/python/en/overview).
* You are *not* allowed to use the `break`-statement. (This hasn't been discussed yet,
but if you happen to know it, don't use it.)
* You are *not* allowed to use the `import`-statement. (This hasn't been discussed yet either.)

## Decomposition
Again, take a couple of minutes of time, before you start coding, to draw the problem with **pen and paper**. Illustrate how you would take on this problem and how you would divide the problem into smaller and simpler steps.

## Hint
Of course you can use the code from the previous exercise. But, you might want to use a `while`-loop in stead of a `for`-loop.

Why is that? In the previous exercise we knew before entering the loop exactly at which year it should end. So, it was easy to define a `range` to loop over. Not so here. Which year do we need to stop? We cannot know this *before* entering the loop.

When does the while loop stop?

## Testing

To be sure to test your program using `checkpy`:

	checkpy birthday
