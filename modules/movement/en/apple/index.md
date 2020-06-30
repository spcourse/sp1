# Apple

Write a program that describes the movement of an apple falling from a height of 100 meters.

    0.00 s til the apple hits the ground
    000.0 km/h is the speed with which the apple hit the ground
    0.00 s elapses before the apple moves 100 km/h


## Background

In physics a lot of research is done on problems that cannot be solved analytically (by hand). Nevertheless, there are a myriad of techniques that, often in a roundabout way, can generate solutions for these problems. In most cases such a technique is very laborious and always involves the aid of computers.

When simulating some physical system you take small steps in time and calculate crudely what happened in between each step. An example of such a system might be the movement of an object. The trick is to make those steps in time as small as possible, which makes the movement increasingly "fluid" as you calculate each step. This task is perfectly suitable for a computer since it involves many (similar) steps. Eventually a simulation describes almost exactly what would actually happen in reality. At least, if the simulation makes use of correct premises and assumptions!



## Specification

Create a file called `apple.py` and declare in it a function `apple()` that performs the necessary calculations. Make sure the results are `print`ed by this function:

1. After how many seconds does the apple hit the ground?

2. At which speed (km/h) does the apple hit the ground?

3. After how many seconds does the apple have a speed of $$100$$ km/h? Is a falling apple therefore faster than a Bugatti Veyron $$2.46$$ seconds) or not?

The output must be very precise and only the requested values may be printed like in the example above.


## Problem analysis

![](GravityOverzicht.png)

Make sure your program takes small steps in time $$\Delta t=0.01$$ seconds) and keep track of the height of the apple ($$x$$) en of the speed with which the apple moves ($$v$$).

Perform for each step in time your calculation in the following order:

1. the force $$F$$ influencing the apple
2. the gravitational acceleration $$a$$ the apple gains
3. the new speed $$v$$ the apple gains, where $$v_{\rm new} = v + a \Delta t$$
4. the new position $$x$$ the apple has, where $$x_{\rm new} = x + v \Delta t$$

Step 1 and 2 can be combined, which is why you do not need to know the mass of the apple for this simulation!

You should then have calculated all information needed of a certain point in time. Subsequently you can make an increment in time and repeat the cycle.


## Hints

* Use the aforementioned formula and start the apple on x = $${\rm R_{earth}}$$ + 100 meters. If you want to know how high up the apple is, use h = x - $${\rm R_{earth}}$$.
* Be careful with the *sign* of the powers and speeds. You start with a positive $$x$$ and move towards $$x=0$$.
* In this case you can also calculate the answers yourself using pen and paper.
* First calculate everything in meters per second (m/s) and convert everything to kilometers per hour (km/h) for specification 2.


## Testing

	checkpy apple
