# Spiral

Write a program that animates a spiraling dot using `matplotlib`. The dot spins with a specific angular velocity around and with each step in time not only changes angle, but also decreases its radius until it eventually arrives exactly in the center:

![](AnimationInspiral.gif)

## Specification

Create a file called `spiral.py` in which the dot is animated as described above.

## Hints

Polar coordinates: a point can be described by way of coordinates $$(x,y)$$, but you could also use two other variables ($$\alpha$$,R), where $$\alpha$$ is the angle with the positive $$x$$-axis and $$R$$ the distance to the origin. The variables can be converted into one another as is described by the following graph.

![](UitlegPolarCoordinates.png)

Details about the animation:

* angle $$\alpha$$ varies from $$0$$ to $$20$$ radians in steps of $$0.1$$
* radius $$R$$ depends on $$\alpha$$, like so $$R=10-0.5\alpha$$

## Testing

This program is completely about the visual aspect and cannot be tested by `checkpy`. You have to have it signed by an Assistant during the practical.
