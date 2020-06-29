# Fractals - Mandelbrot set

You probably already know those beautiful multi-colored pictures in which patterns repeat themselves until they are infinitely small. These incredibly complex patterns, called *fractals*, funnily enough are product of a small set of simple (mathematical) rules. Often times in nature do we find such simple hidden mechanisms for complex phenomena, however hard they are to find out about. In this assignment we delve a little deeper into the math behind fractals and with that knowledge we'll try to recreate one of the most well-known fractals: the [Mandelbrot set](https://en.wikipedia.org/wiki/Mandelbrot_set).

<p align="center">
![](mandelbrot.png){: style="width:50%"}
</p>

The goal of this extra assignment is: write a program `fractal.py` that displays the Mandelbrot set on the screen.

### Mathematical intermezzo: complex numbers

To get a better understanding of the math behind a fractal, we must first introduce a new mathematical concept: *complex numbers*.

Complex numbers maintain a special place in math and can be found in many subject in mathematics as well as physics. During the lectures you'll get to see many more characteristics, but here we introduce the bare minimum.

   - definition: we define $$ i = \sqrt{-1}$$
   
A complex number (z) is made up out of two components: a real and an imaginary part.

   - complex number: z = $$\alpha + \beta i$$

, with  $$\alpha$$  the real and  $$\beta i$$  the imaginary part.

A common way to imagine these numbers is the so called *complex field*, a 2-dimensional field with a real axis and an imaginary axis that represents the complex part of the number, as can be seen below. Two examples of complex numbers are $$c = -5 + 3i$$ and $$c=-2-4i$$. These are both represented in blue. All numbers we usually use (0, -3, $$12/67$$, $$\pi$$, $$e$$, 10465, ...) are situated on the real axis. There are also a couple of complex numbers in red; we'll come back to those in time.

<p align="center">
![](ComplexeGetallen.png){: style="width:70%"}
</p>

Adding complex numbers is simply adding the real part and the complex part individually, but multiplying them requires some caution. You have to take into account that $$i^2 = -1$$. It's most apparent when performing exponentiation:

   * squaring: $$(\alpha + \beta i)^2 = (\alpha^2 - \beta^2) + (2 \alpha \beta)i$$

For example: $$(2+i)^2 = 3+4i$$. If you were to add the original number $$(2+i)$$ to it again the result would be $$5+5i$$. These numbers are all three denoted in red in the figure of the complex field above. These calculation are the ones we'll be performing in the assignment.

This is all of the mathematical background on complex numbers you'll be needing for this assignment. Now we can get to work.


### Functions for complex numbers, sequences and fractals

Just like for normal numbers, functions can be defined for complex numbers too. In this assignment we'll work with polynomials like the following one:

   $$f(z) = z^2 + c$$ 

, in which both $$z$$ and $$c$$ are complex numbers. The only freedom we have left is the choice in the value of the number $$c$$. The outcome of the function is once again a complex number.

**Sequences:**

By feeding back the outcome of the operation (function) as an argument into the function itself we're given a sequence of numbers.

   - step 1: choose a complex number $$z_0$$
   
   - step 2: calculate $$f(z_0) = z_0^2 + c$$. We call this number $$z_1$$.   

   - step 3: calculate $$f(z_1) = z_1^2 + c$$. We call this number $$z_2$$.   

   - step 4: ...

In a general sense we denote repeating the function $$n$$ times as follows: $$z_n = f^{(n)}(z_0)$$. For each starting number in the complex field we can now examine how the sequence develops.

**Fractals (globally):**

For each choice of a function $$f(z)$$ we can divide the points in the complex field in two groups. To be precise: for a specific (starting) point $$z_0$$ the following applies:

   - the sequence converges:  $$\rightarrow$$  $$z_0$$ **is** member of the set

   - the sequence diverges: $$\rightarrow$$ $$z_0$$ **is not** member of the set

By subsequently assigning a color code to the speed with which a specific starting point in the complex field either diverges or converges, each point in the complex field is assigned a color. Plotting these points create the famous fractals we know.


**The Mandelbrot set:**

 
The Mandelbrot set is defined by a function we've already seen before, with a special choice for constant $$c$$. The starting point itself to be precise. $$c = z_0$$ should then give:
    
   Mandelbrot: $$f(z) = z^2 + z_0$$ 
    
, in which $$z_0$$ is the starting point. 

For any particular starting point the sequence can diverge or converge. As an example of both cases, you will find the first 10 points in the sequence for the two starting points $$z$$ (= $$z_0$$) = $$-0.20 + 0.25i$$ and $$z$$ (= $$z_0$$) = $$0.50 + 0.25i$$.

      z0 = -0.20 + 0.25i       z0 = 0.50 + 0.25i
      ------------------       ------------------

    z0 = -0.200 + 0.250 i      z0 =  0.50 +  0.25i
    z1 = -0.223 + 0.150 i      z1 =  0.688 + 0.500 i
    z2 = -0.173 + 0.183 i      z2 =  0.723 + 0.938 i
    z3 = -0.204 + 0.187 i      z3 =  0.143 + 1.605 i
    z4 = -0.193 + 0.174 i      z4 = -2.055 + 0.710 i
    z5 = -0.193 + 0.183 i      z5 =  4.221 + -2.669 i
    z6 = -0.196 + 0.180 i      z6 = 11.190 + -22.279 i
    z7 = -0.194 + 0.180 i      z7 = -370.655 + -498.339 i
    z8 = -0.195 + 0.180 i      z8 = -110956.038 + 369424.274 i
    z9 = -0.195 + 0.180 i      z9 = -124163052007.623 + -81979707256.034 i

Now it's time to draw a fractal for yourself.

### Assignment: 

Create a program called `fractal.py` and determine for each point $$z_0$$ in the complex field whether the sequence converges or diverges for the polynomial of the Mandelbrot set:

   $$f(z) = z^2 + z_0$$. 
    
If the sequence converges you should draw the point in blue, else if it diverges you have to draw the point in white.

Although you'll have to determine which definition of convergence for yourself in this assignment, the speed with which this happens will be ignored in this assignment. As a result the plot will only consist of two colors. Somewhat more boring than the official plot of course, but plenty challenging enough for this assignment.

**Specification for the scan (plot):**

The resolution of the graph needs to have the following dimensions:

    - real axis:      600 points between -2.00 and 1.00 

    - imaginary axis: 600 points between -1.50 and 1.50 


If you've finished the assignment early you can opt to add more color to your plot. Take into account the speed of divergence and let that added bit of information influence the color of a point. Have fun!

## Checkpy

This assignment does not have a checkpy to check your solution. You're on your own.