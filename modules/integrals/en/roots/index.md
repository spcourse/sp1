# Roots

Write a program that calculates and shows the roots (the locations where
a function intersects the x-axis) of the quadratic function $$f(x)=x^2+2x-10$$.

    # python roots.py
    The roots are -4.32 and 2.32

![](../../assets/PolynoomAnalyse.png)


## Specification

* Call your program `roots.py`.

* Create one function `roots(a, b, c)` that can calculate the roots of *any*
quadratic function of the form $$f(x)=ax^2+bx+c$$. There are two possible
results the function could `return`:

    * an empty list `[]` when the function has no roots
    * a list of two elements `[n1, n2]` in which `n1` and `n2` are the roots of the function

* Your programs should then use this `roots()` function to calcuate the roots
for $$f(x)=x^2+2x-10$$. Print out both roots, plot this function and clearly
display the roots in the graph that you calculated.

## Hints

* Calculate the roots with use of the [quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula).

    * In what case does this formula indicate there are no (real-valued) roots?

* To make sure you can show the computed answer neatly, call the function and store the result in a variable, as in the example below:

        result = roots(1, 2, -10)

* Later on also test your program with a quadratic function that has no roots (check if the list is empty). The program should print that the roots do not exist:

        This function does not have roots.

## Testing

If you use `checkpy`, note that it does not check if you program has the correct output. It does check if the function `roots()` returns the correct result.

    checkpy roots.py

(If it doesn't work, try updating your checks using the command `checkpy -u`.)
