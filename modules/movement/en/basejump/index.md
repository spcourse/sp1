# Free fall during a base jump

Write a program in which the fall of a basjumper is calculated. The basejumper is jumping from the top of Burj Khalifa in Dubai (828 m). Assume this base jumper weighs 72 kilograms.


## Background

In the previous assignment the air friction was neglected, which made it possible to verify the answer using relatively simple physics equations. Now we're going to add back a layer of realism: air friction.

The aerodynamics that a falling object is subject to is proportionate to the square of its speed:

$$F = \xi v^2$$, where $$ \xi = 0.24$$

Although air resistance is dependent on the surface and mass of the object and the density of the air, we'll only be examining the effect of speed in this assignment. Because of the friction, there exists a speed in which gravity and air friction keep each other in balance. The maximum speed a parachutist can achieve is about 196 km/h and is called [terminal velocity](https://en.wikipedia.org/wiki/Terminal_velocity). 

![](Freefall.png)

As always there are people trying to find the [limits](https://en.wikipedia.org/wiki/Speed_skydiving). Because he started his jump in an area where air pressure was incredibly low, Felix Baumgartner reached a record speed of 1357.64 km/hour, that will be very difficult to overcome.


## Specification

Create a file `basejump.py` and declare a function `basejump()` in it. Follow the same strategy as in the assignment **Apple**, but this time take the aerodynamics into consideration using the provided formula.

### Graphs

You should have the following graphs **checked** by an Assistant:

1. Plot a graph of the speed as function of time.

    Test your program by pretending the tower is 2000 meters high and see if you indeed find the terminal velocity of 196 km/h.

2. Plot a graph of the height as function of the time.

    Draw two lines in the same figure: in green/blue the scenario when we ignore/apply air friction.

### Simulation

`Print` the answers to the following questions. Make sure to be precise and only provide the requested values by `print`ing each on their own separate lines.

The base jumper is in free fall first, but 100 meters away from the surface they open their parachute.

* How much time (seconds) does the jumper have from the moment they jump to this moment, if we ignore any air resistance?

* How much longer (seconds) does the base jumper have to enjoy their free fall because of air resistance?

## Testing

	checkpy basejump
