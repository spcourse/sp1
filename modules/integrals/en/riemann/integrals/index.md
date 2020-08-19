# Riemann

Write a function that uses a Riemann sum to approximate the integral of a
quadratic function within specified boundaries, i.e.

$$\int_{d}^e (a x^2 + bx + c)~dx$$

Here, the values $a$, $b$, and $c$ define the quadratic function, while the parameters $d$ and $e$ indicate the lower and upper bound of the integral
respectively.

The program should print out the approximated integral and a plot of the
quadratic function should also be displayed on the screen.

## Specification

* Create a new file called `riemann.py`.

* Declare a function called `riemann()` that can calculate integrals using the Riemann sum.

    * The function `riemann()` has to accept 6 arguments:

        - `a`, `b`, and `c`, the parameters of the quadratic function
        - `d` start of the integral area
        - `e` end of the integral area
        - `n` number of rectangles used to approximate the integral

    * The function `riemann()` should plot the quadratic function on the screen.

    * The function `riemann()` should `return` the approximate value of the integral.

* Your program should call the Riemann function to approximate the integral for several quadratic functions

## Testing

First, test your program on some integrals for which you know the correct
result beforehand. You can use the example functions from the introduction for
this, or use your own.  Once the program correctly calculates the known
integrals, you can try the unknown new integrals.

$$\int_{0}^5 2x~dx = 25$$

$$\int_{-2}^3 (-x^2 + 4x + 15)~dx \approx 73.33$$

$$\int_{-2}^3 (-x^2 - 8x + 8)~dx \approx 8.33$$

Add these functions to your own program and make sure to repeatedly call the
`riemann()` function at the bottom of your file, to verify each of these
examples.

## Debugging

Does there appear to be some error or bug?

* Visually check the graph of the integral whether the answer is anywhere near what is to be expected.

* If that appears to be the case, then it could be possible that the number of steps is too small to come to an exact enough answer. Try again after increasing the number of steps (or, rectangles) and see how that influences the outcome.

## Testing
Once you convinced yourself it worked you can use checkpy to run some automatic tests.

	checkpy riemann
