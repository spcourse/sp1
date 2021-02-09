# The thousandth prime

The first prime number is 2, the third prime number is 5, the 1000nd prime number is 7919. Implement a program that generates the $$n$$-th prime number, where $$n$$ is a user provided value.

    Which prime number are you looking for? 1000
    7919

## Background

As previously mentioned, a computer is a great tool for quickly executing a series of "dumb", or simple, actions. An example of what a computer does a lot better (and quicker!) than humans, is calculating prime numbers. The definition of a prime number is not too complicated. But determining how many divisors a number has could take an enormous amount of time. Python to the rescue!

## Specification

* Ask the user to provide the rank (how many-th) of the prime number that they want. This has to be a whole, positive number.

* If a user provides a value that is not valid, ask the user to try again (you may assume the user gives a whole number as input, not a decimal or word). Keep prompting the user for a value until they do provide a valid number. Since it is not known how often you'll have to repeat the question, a `while`-loop seems perfect!

* Once the rank of the prime is established, have your program calculate the correct prime and report it back to the user.

* Make sure that your program does not output anything other and the prime number, just like in the examples at the start!

### Constraints

The same as before:

* You are only allowed to use the concepts that are discussed in this module.
For an overview of those concepts have a look [here](/python/en/overview). Note that this doesn't include lists! You'll learn about those after this exercise.
* You are *not* allowed to use the `break`-statement.
* You are *not* allowed to use the `import`-statement.

## Problem analysis

As always, take a couple of minutes of time, before any coding, to draw the problem with **pen and paper**. How would you divide the problem into smaller and simpler steps.

In this assignment, for one last time we'll guide you through some of the steps.

## Step 1: prime-check

An important part of the description above is the fact that it's about prime numbers. What is a prime number? We'll have to express that concept in Python.

So it is key to first write a program that can determine whether a particular number is a prime or not. At the end of the program it should be clear, through display on the screen, if the number is a prime or not. It starts with the variable `number`, in which we store the number that must be investigated:

    number = input("Enter a number: ")
    number = int(number)
    # TODO: this is where your code goes

If the user enters the number 37, at the end of the program the following statement should be printed:

    The number 37 is a prime number

In the case of a non prime number, such as 36, it should print:

    The number 36 is not a prime number

At the start, keep it simple. Use a `for`-loop and `%` (modulo) to determine how many numbers are a divisor of `number`. If you keep track of this in the loop (count!), then by the end of the loop you can determine if a number is prime or not. Ultimately print the conclusion, like in the example above.


## Step 2: check all numbers smaller than 100

Let's take it a step further. We can reuse our code from before and for *each* number smaller than 100 determine whether it is a prime number or not.

Create an extra `for`-loop to check each number smaller than 100 and determine for each of these "candidate primes" whether it is or isn't a prime number. For each number you'll have to determine the divisors individually, so you'll be needing two `for`-loops inside of one another (*nested loops*).

Implement aforementioned procedure and make sure it works correctly. Next we'll want to expand the procedure by `print`ing each found prime number. So after each conclusion of whether a number is a prime, we'll need a `print`-statement.

Is your answer correct? Verify on the web!

## Step 3: the umpteenth prime

Now let's get back to the assignment: finding the n-th prime number. We'll assist you a bit in the strategy for the program:

* You cannot simply loop with a `for`-loop til `n`. Since we ant the `n`-th prime number; we don't want to know if `n` is a prime number (see the difference with step 2?). So you'll have to keep count *how many* prime numbers you've already found. Use a variable for this.

* Start out small. Make sure your program works for the first 10 prime numbers before you start looking at 10 thousand numbers. Ten is just large enough to test most of the programs functions and small enough that it should be easy to fix mistakes.

* Errors? Print for every candidate-prime some information, so you know what calculation your program is at, than see if your intended strategy is working correctly.

> Maybe it is weird or annoying to write a program, after which you find out that it doesn't work correctly. That is a programmers fate: it's just incredibly difficult to precisely formulate an algorithm and instantly convert it into functioning code. Sometimes you've forgotten an exception or edge case, but just as easily you've made a typo somewhere. Keep in mind even the best programmers have to deal with this!

## Step 4: does it really work?

Once again carefully read the specification at the top of the assignment and make sure your program works exactly as specified.

Then you're all set to test:

  checkpy prime

## Step 5: small optimizations

We started out as simple as possible, to get to a *correct* program as soon as possible (checked by `checkpy`). But through some mathematical insight we could do some small optimizations, increasing the speed of the program.

* Except for 2, *even* numbers are never a prime number (this should only be a small adjustment to your code).

* If you find a divisor (that is not 1 or the number itself), there is no reason to look for any other divisors, it is already certain that number is not a prime.


## Hints

* You only need the Python elements you've learned up until now to correctly implement this program!

## Testing

To be sure test your program again using `checkpy`:

    checkpy prime
