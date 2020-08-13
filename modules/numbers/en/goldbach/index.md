# Goldbach

Write a program called `goldbach.py` that proves Goldbach's conjecture to be true for all even numbers up to and including 1000.

    # python goldbach.py
    16 = ...
    18 = 5 + 13
    20 = 3 + 17
    22 = 5 + 17
    24 = ...

## Background

Goldbach's conjecture is one of the oldest unsolved problems in mathematics. Goldbach posed:

*"Every even integer greater than 2 can be expressed as the sum of two primes."*

A prime number can also be used twice (6=3+3). Although this conjecture does indeed seem to be correct for all numbers up to $$4\cdot10^{18}$$, there still is no analytical proof for this hypothesis. A computer is unfit to proof the conjecture (after all it cannot count till infinity), but you could disprove the conjecture by identifying an even number that cannot be expressed as the sum of two primes. We're going to lend our hand in this search.

## Specification

Write a program to show that all even numbers up to and including 1000 can indeed be expressed as the sum of two primes. More specific: show for each even number *explicitly* (on the screen) that it can be written as the sum of two primes, like in the example above.

More important is of course if or when you find a number that *isn't* in compliance with Goldbach's conjecture. Make sure that your program clearly displays such a finding on the screen. Bingo!

## Hints

* Always work out the problem with pen and paper before coding. The 5-10 minutes spent on drawing out your ideas are earned back when you convert them into code.

* Use a list of primes as the base for this program. Think for yourself up to what number the list should go to provide all even numbers through 1000 of divisors.

* For this assignment you're allowed to use the following Python construction, that checks whether an element is or isn't found in a list. The following code will print to the screen whether 7 is indeed a prime number.

      primes = [2, 3, 5, 7, 11]
      x = 7
      if x in primes:
        print(f"Yes, the number {x} is found in my list of primes.")

  And if you'd want to check for all numbers from 1 through 12 whether they're found in the list, you use:

      primes = [2, 3, 5, 7, 11]
      for x in range(1, 12):
          if x in primes:
              print(f"Yes, the number {x} is found in my list of primes.")

  Clearly we don't hand you this hint without a reason. This assignment has a more 'elegant' solution in which this construction is used. You can also solve it in a less elegant way (brute-force) of course.

## Testing

Once again carefully read the specification at the top of the assignment and make sure your program works exactly as specified.

Now you're ready to test:

    checkpy goldbach
