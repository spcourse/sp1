# Assignment: the ultimate free fall

The apple from the previous assignment reached the surface after a little over 4 seconds. Imagine that exactly at the location where the apple was dropped, a tunnel was dug straight through the planet.

Write a function called `tunnel()` in a file called **tunnel.py** that describes the movement of the apple through earth. The apple moves along the $$x$$-axis, where $$x=0$$ in the center of the earth. The apple starts with a speed of $$0$$ at a height of $$0$$ meters above the surface of the earth. What exactly happens?
 
![](EarthHole.png)

## Output

1. Create a graph of the speed of the apple as function of time.

2. Create a graph of the position as function of time.

3. Calculate the maximum speed that the apple reaches (km/h) and `print` it.

4. How long does it take for the apple to be back in the position you let go of it (seconds)? `Print` the answer.

## Tips

* Ignore air resistance for this assignment.

* The effective mass of the earth, the mass 'that pulls at you' becomes smaller the closer you get to the center. So: if the earth weighs $$M_{\rm earth}$$ and you traveled 50% of the distance to the center of the earth, earth now only 'weighs' $$\left(\frac{1}{2}\right)^3M_{\rm earth}$$ in Newtons formula.

* Assume earth is a globe with constant density.

## Physical (h)in(d)sight

Even though this seems like a difficult problem, it was still possible to solve it with pen and paper. The effective force that is applied to a particle grows linearly as a function of distance to the center of the earth. If a particle from the center of earth ($$x=0$$) moves outward (position $$x=r$$) the following applies:

  * The effective gravitational constant grows like $$r^3$$, because the effective mass of the globe that pulls the object grows with $$r^3$$. Ergo: $$F\propto r^3$$.

  * The force itself diminishes with $$1/r^2$$ because the force decreases inversely proportional to the square of the distance. Ergo $$F\propto r^{-2}$$.
  
Eventually the force on a particle that continually moves away from the center will decrease linearly with distance. That is exactly the same scenario as with a classical spring for which we do know the equation of motion: [Hooke's law](https://en.wikipedia.org/wiki/Hooke%27s_law).


## Testing

	checkpy tunnel