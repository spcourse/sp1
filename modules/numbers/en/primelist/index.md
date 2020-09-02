# List of primes

Write a program called `listprimes.py` that asks the user to provide a number $$n$$ and generates a list of all the primes between 2 (inclusive) and $$n$$ (exclusive).

    Example:
    Enter a number: 11
    [2, 3, 5, 7]

## Specification

* Ask the user to provide a number. This has to be a whole number bigger than 2. If a user provides a value that is not valid, ask the user to try again (you may assume the user gives a whole number as input, not a decimal or word).

* Generate a list with all prime numbers $$p$$, $$2 \leq p<n$$, in ascending order. (You are required to use a list for this exercise.)

* Print the list.

## Testing

To be sure test your program again using `checkpy`:

    checkpy listprimes

## Extra challenge (not required)

For this assignment, clever algorithmic thinking can make a real difference. There are a lot of correct ways to generate a list of primes, but some solutions are much faster than others.

If you finished the **entire** module, and you have time to spare. You can challenge yourself by making your code more efficient. You could have a look at the [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes).

Make sure that you don't try this until everything else is finished, and that you backup your old solution.

Note that do not get any extra credit for implementing a faster algorithm. You do this only as a challenge for yourself.
