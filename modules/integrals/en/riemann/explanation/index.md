# Riemann

One of the ways of evaluating an integral is by expressing it as the sum of small rectangles, the Riemann sum. Imagine the following integral:

$$ \int_a^b f(x)~dx $$

Then: divide the interval $$ (a,b) $$ into $$N$$ intervals of equal length $$\Delta x$$ and write the integral as the sum of all partial integrals of each interval.

$$ \int_a^b f(x)~dx = \sum_{i=0}^{N-1} \int_{x_i}^{x_{i+1}} f(x)~dx ​$$

For which $$x_i$$ is the corner of one of those intervals. There are $$N+1$$ corners that range from $$ x_0 $$ through $$x_{N}$$. As can be seen in the graph on the following figure.

![](../../../assets/RiemannExample.png)

Now that we know we're looking for a large number of partial integrals, let's simplify the problem at hand, by *approximating* the partial integrals.

We imagine them as a rectangle. The width of the rectangle is of course $$ \Delta x = (x_{i+1} - x_{i})$$. A (simple) estimation of the height of the rectangle that best represents the integral on this small interval is simply the average of the value of $$f(x)$$ at the left hand side and right hand side of the interval. The integral on the partial interval can then be written as:

$$ \int_{x_i}^{x_{i+1}} f(x)~dx = \frac{f_{i+1}+f_i}{2}~\Delta x$$

The complete integral is then expressed by:

$$ \int_a^b f(x)~dx = \frac{\Delta x}{2} (f_0 + 2 f_1 + 2 f_2 + ... +  2 f_{N-1} + f_N)~+~\mathcal{O}((\Delta x)^2)\\
                       ~~ \approx \Delta~x(f_1 + f_2 + ... +  f_{N-1}) ~+~ \frac{\Delta x}{2}(f_0+f_N) $$

In the evaluation of the integral $$ \int_{0}^{\pi}sin(x)~dx$$, we have divided the integral area $$x$$ in 13 areas of similar size. Which means we have 14 x-values. The height of each of the 13 rectangles (or, smaller integration areas) is the average of the function's value on the left hand side and right hand side of the rectangles. 

The trick is as follows: the ultimate integral can be evaluated by the sum of the areas of all rectangles. Note that when calculating the integral the 'areas' of rectangles underneath the y-axis is negative. When the intervals become smaller and smaller, the approximation of the integral gets more precise! Which is why it's a good thing we are using a computer for this.
