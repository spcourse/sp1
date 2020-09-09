# The twitter egg!

Write a function called `twitter.py`. The program calculates the area of the Twitter egg. The circumference is determined by:

$$ \sqrt{x^2+y^2} + \frac{2}{3}\sqrt{x^2+\left(\frac{5}{6}-y \right)^2 } = 1$$

![](../../../assets/TwitterEiCombi.png)

Generate a total of 1 million points and calculate the correct area. After each 1000 generated points, store the estimation of the area at that moment. If implemented correctly, your answer should converge and you should see the estimation improve after each iteration.

Your program consists of three parts:

* `print` the answer of the area to the screen, 2 decimals precise.
    The area of the Twitter egg is x.xx

* Plot the distribution of correct and incorrect points (as per the example above).

* Also display in the graph what the area is. Once again 2 decimals precise.

## Hints

Estimating this area can of course be done with a method very similar to Monte Carlo integration. Some
quick questions to consider if your answers seem incorrect:

* What is the difference between the area calculation here and integration?

    * What does that mean for how *negative* area should be handled?

* What would be a sensible surrounding area to use for the egg?

    * How could determine some sensible values to use as bounds?
