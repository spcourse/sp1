# Riemann

Write a function that uses a Riemann sum to calculate the integral of a random mathematical function with specified integral boundaries. The mathematical function should also be displayed on the screen.

## Specification

* Create a new file called `riemann.py`.

* Declare a function called `riemann()` that can calculate integrals using the Riemann sum.

* The function `riemann()` has to accept 4 arguments:

	- `func` a function of which the integral is calculated
	- `a` start of the integral area
	- `b` end of the integral area
	- `n` number of squares used to calculate the integral

* The function `riemann()` should `return` the correct value of the integral.

* The function `riemann()` should display the mathematical function on the screen.


## Testing

Test your procedure using the following function, which is easy to analytically verify:

	def func1(x):
		return x**2

Also test your program with the following functions. Some of them are integrable, others can only be approximated numerically.

$$\int_{0}^{1}x^2 dx$$

$$\int_{0}^{1}x^{x+\frac{1}{2}} ~dx$$

$$\int_{0}^{\pi}sin(x) dx$$

$$\int_{0.2}^{2.2} \tan(\cos(\sin(x))) ~dx$$

$$\int_{0}^{\pi} \sin(x^2) ~dx$$

Add these functions to your own program and make sure to repeatedly call the `riemann()` function at the bottom of your file, to verify each of these examples. You can pass `func1()` to your `riemann()` function as follows:

    riemann(func1, 0, 1, 10000)

## Hints

* Note: when you divide the interval in $$N$$ parts, there will be $$N+1$$ corners.

* Create a graph of the function so you have a clear view of what area you are integrating. You can add a bit of code to the `riemann()` function to plot said graph.

* First test your program for an integral of which you know the outcome beforehand. For a few of the example functions above that should be the case. Once the program correctly calculates the known integrals, you can try the unknown new integrals.


## Debugging

Does there appear to be some error or bug?

* Visually check the graph of the integral whether the answer is anywhere near what is to be expected.

* If that appears to be the case, then it could be possible that the number of steps is too small to come to an exact enough answer. Try again after increasing the number of steps (or, rectangles) and see how that influences the outcome.


## Testing

	checkpy riemann
