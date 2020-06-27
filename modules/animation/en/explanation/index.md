# Animations

Although a graph is a very useful tool to visualize a simulation, sometimes it's more insightful to make an animation. Python offers the possibility to redraw a figure again and again. That gives a multitude of possibilities to create movement. We will demonstrate a small example, in which we move a line (and point) along $$f(x)=sin(x)$$ over the screen. We build up the function in 3 steps, where in each step we add 1 element. With the help of this functionality you can create an array of animations.

## A moving dot

When you draw a point (one $$x$$-value and one $$y$$-value) of which the $$x$$ and $$y$$ change over time, then the point appears to move over the screen. In the code below we let $$x$$ increment, calculate $$y$$ and draw the point on the screen. We also use commands `xlim` and `ylim` to specify in the plot what $$x$$-values and $$y$$-values we want to display. 

    import math
    import numpy as np
    import matplotlib.pyplot as plt
    
    # take small steps in x between 0 and 2pi
    for x in np.arange(0, 2 * math.pi, 0.05):

        y = math.sin(x)

        # plot graph
        plt.plot(x, y, 'bo', markersize = 10)  # blue point
        plt.xlim(0, 2 * math.pi)
        plt.ylim(-1, 1)

        # update graph
        plt.draw()
        plt.pause(0.001)

        # clear graph
        plt.clf()

![](../../assets/AnimationExampleSin1.gif)

> As you can see, we call the function `pause()` in our code. We do this to give pyplot the opportunity to draw a new figure on the screen. This only happens during the pauses we give to pyplot.


## A moving line

Creating a graph by using lists: a list of $$x$$-values and a list of $$y$$-values. If you repeatedly expand those lists you get the following effect: the function $$f(x) = sin(x)$$ represented by a red line:

    import math
    import numpy as np
    import matplotlib.pyplot as plt
    
    x_coords = []
    y_coords = []

    # take small steps in x
    for x in np.arange(0, 2 * math.pi, 0.05):

        y = math.sin(x)

        x_coords.append(x)
        y_coords.append(y)

        # plot graph
        plt.plot(x_coords, y_coords, 'r-')   # red line
        plt.xlim(0,2 * math.pi)
        plt.ylim(-1, 1)

        # update graph
        plt.draw()           
        plt.pause(0.001)

        # clear graph
        plt.clf()            

As you can see, the code only changed by three lines as opposed to example 1. The result is as follows:

![](../../assets/AnimationExampleSin2.gif)

## A dot, a line and text

You can also draw the dot and the line at the same time as well as display information to the screen about the $$(x,y)$$ position of the dot on the screen.

    import math
    import numpy as np
    import matplotlib.pyplot as plt
    
    x_coords = []
    y_coords = []

    # take small steps in x
    for x in np.arange(0, 2 * math.pi, 0.05):

        y = math.sin(x)

        x_coords.append(x)
        y_coords.append(y)

        # plot graph
        plt.plot(x_coords, y_coords, 'r-')               # red line
        plt.plot(x, y, 'bo', markersize = 10)  # blue dot
        plt.xlim(0, 2 * math.pi)
        plt.ylim(-1, 1)

        # text on the screen      
        plt.text( 0.25, -0.8, "(%.2f,%.2f)" % (x, y) )  

        # update graph
        plt.draw()           
        plt.pause(0.001)

        # clear graph
        plt.clf()

![](../../assets/AnimationExampleSin3.gif)
