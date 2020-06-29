# Monte Carlo

Write a function that, by way of the Monte Carlo method, calculates the integral of a random mathematical function with specified integral boundaries. Take care that both the function as well as the generated random points (both the 'correct' and 'incorrect' ones) are displayed on the screen.

## Specification

* Create a new file called `montecarlo.py`.

* Declare a function called `montecarlo()` that can calculate integrals by using a Monte Carlo simulation.

* The function `montecarlo()` should accept five arguments:

	- `func` a function of which the integral will be calculated
	- `x1` the first x value
	- `y1` the first y value
	- `x2` the second x value
	- `y2` the second y value

* The function `montecarlo()` should `return` the area under the graph.

* The function `montecarlo()` should plot the function and the points *within* the integral area (the 'correct' points) in green and the point *outside of* the integral area (the 'incorrect' points) in red.


## Testing

Test your procedure using the following function, which is easy to analytically verify:

	def func1(x):
		return x**2

Also test your program with the following functions. Some of them are integrable, others can only be numerically approximated.

$$\int_{0}^{1}x^2 dx$$

$$\int_{0}^{1}x^{x+\frac{1}{2}} ~dx$$

$$\int_{0}^{\pi}sin(x) dx$$

$$\int_{0.2}^{2.2} \tan(\cos(\sin(x))) ~dx$$

$$\int_{0}^{\pi} \sin(x^2) ~dx$$

Add these functions to you own program and make sure to call `montecarlo()` a number of times at the bottom of the file, to verify each of these examples.

## Hints

* Create a graph of the function so you have a clear view of what area you are integrating.

* Also create a graph with red and green points like in the example in the theory section. Should you have made a mistake in your logic, you can immediately see it in the graph, instead of having to spend hours looking at your code to find the bug.

* When encountered with 'negative integral areas' you can split the areas.

* For research applications the size of the rectangle around the integral area is chosen as tight as possible to maximize efficiency.

* First test your program for an integral of which you know the outcome beforehand. For a few of the example functions above that should be the case. Once the program correctly calculates the known integrals, you can try the unknown new integrals.

* Think carefully how to deal with parts of the integral area that are situated below the y-axis.

## Testing

	checkpy montecarlo
