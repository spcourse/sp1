# Coprimes

Write a program called `coprime.py` that calculates the chance that two random whole numbers **do not** have a common divisor. Such a pair of numbers is called a **coprime**.

    #python coprime.py
    The chance that two random numbers do not share a common divisor is:
        - prediction (mathematical): 0.xxx
	    - empirical (Python): 0.xxx 

Although we want to leave this assignment up to you for as much as possible (there is no `checkpy`), we'll still give some intermediate steps for the first extra assignment.

### Definition of the coprime and predictions from numbers theory
	    
In the description on the definition of [coprimes](https://en.wikipedia.org/wiki/Coprime_integers) on Wikipedia we see there is a way to calculate the chance that *n* random numbers do not share a common divisor.

This chance is: $1$/\zeta(n)$$, where $$\zeta(n)$$ is the well-known [Riemann zeta function](https://en.wikipedia.org/wiki/Riemann_zeta_function).

**Specific case: two numbers (n=2)**:

The chance that two random numbers do not share a common divisor is:

$$1/\zeta(2) \approx 0,608$$.

In this assignment we are going to verify this calculation. First we'll find out how to determine whether two numbers share a divisor and by later doing so for large number of random number-pairs we can calculate the chance such numbers will be coprimes. With that we can verify whether the prediction from numbers theory is actually correct.

### Finding the solution yourself

There are different methods to solve this problem. For now, follow the following procedures and intermediate steps, because those will aid us in verifying how far you got into solving this problem.


#### step 1: list of prime factors

Every number can be expressed as a unique product of prime numbers:

        34 = 2 x 17
        88 = 2 x 2 x 2 x 11
     79220 = 2 x 2 x 5 x 17 x 233

Declare a function called `prime_factors(number)` that finds the list of prime factors (divisors) for a particular number and `print`s them to the screen.

    python> prime_factors(79220) 
            Prime factors of  79220  =  [2, 2, 5, 17, 233]

Make sure that the function also `return`s the list of prime numbers. The rest of the program will be using that list.
 
#### step 2: finding common divisor of two numbers

Write a function `divisor_count(n1, n2)` that, for now, determines if there exist any common divisor or not. Use the function you've declared earlier `prime_factors()` to first generate the list of prime factors for those numbers. Then find the numbers present in both lists.

It's not yet important to get the exact number of common divisors. For this assignment it is only import to know if there are *no* common divisors. If so, the function should return a `0`.

#### step 3: testing the hypothesis for a large number of pairs

To determine the fraction of pairs where there are no common divisors we'll have to:

   1. create a large amount of number-pairs (randomly)

   2. check whether there are any common divisors for each number-pair

   3. evaluate which fraction of number-pairs had no common divisors 

Create a function `experiment()` that implements each of these steps and that `print`s the fraction on the screen after which it `return`s that fraction.

Specifications:

    - use numbers (n1 and n2) between 10.000 and 100.000

    - use 10.000 number-pairs


**Python tip:**

One of the components we need, generating a random number, is something we'll work with in module 2. In this case it's even more specific, a random *whole* number to be exact.

Add the following line of code to the top of your file to be able to use the `random`-library in your own code. This library contains all sorts of different functions that generate random numbers.
 
        from random import random
        
The function we need is `randint(a,b)` that generates a integer between `a` and `b` including both values. In this exercise we'll use a n_min (`a`) = 10000 and n_max (`b`) = 100000. To assign such a random number the name `n` you can use the following lines of code: 

        n_min = 10000
        n_max = 100000
        n = random.randint(n_min, n_max)        
        

#### step 4: theoretical prediction

Write a function `prediction(n)` that predicts the theoretical chance of `n` numbers having no common divisors. This consists of not much more than calculating the Riemann zeta function yourself and with that determine the correct chance. Once again `return` this value.

#### step 5: Put everything together

By calling the two functions `experiment()` and `prediction()` everything should fall in its place. The screen should now display (3 decimals accurate):


    The chance that two random numbers do not share a common divisor is:
        - prediction (mathematical): 0.xxx
	    - empirical (Python): 0.xxx 

## Checkpy

This assignment does not have a checkpy to check your solution. You're on your own.
