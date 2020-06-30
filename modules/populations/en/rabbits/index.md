# Population dynamics: predator-prey model

A classical example of a complex dynamical system is the so-called predator-prey model. The basis of the mathematical description of the populations are the famous [Lotka-Volterra equations](https://en.wikipedia.org/wiki/Lotka–Volterra_equations). The math quickly become very complex and it's not always as easy to predict what the effects of a change of behavior are on the different populations in a system.

In this module we'll create a simulation ourselves of a well-organized system: a forest of 100 by 100 meters inhabited by 25 rabbits and 2 foxes. By programming it ourselves, we can add new phenomena. Visualizing the system gives us direct feedback on our code and shows us the consequences of the new behavioral elements that we add. The goal of this module is to add complexity to the behavior of rabbits and foxes in our simulation and to ultimately find out whether the foxes or the rabbits will emerge victorious when released in our isolated neck of the woods.

## Start: two moving rabbits on your screen ##


> Note: animations cannot be created in the online Python IDE! You'll need a local installation on your own computer. Don't hesitate to send us an email if you need any assistance.

We start out this module, against the philosophy of this course, not with an empty screen, but with the following bit of code. Not because it is terribly difficult, but because we then have a common start and can all add pieces of code in the same manner.

{: .language-python}
    import matplotlib.pyplot as plt

    # lists you want to be accessible from all parts of your code are:
    global positions_rabbits_x, positions_rabbits_y

    #-------------------
    def predator_prey():
    #-------------------

        # retrieve the 'shared' lists defined above
        global positions_rabbits_x, positions_rabbits_y

        # define the starting position of rabbits (x-position and y-position at t=0)
        positions_rabbits_x = [10.,60.]  
        positions_rabbits_y = [ 2.,10.]  
   
        # take steps in time
        for i_time in range(10):

            # move the rabbits
            move_rabbits()    

            # plot the position of the rabbits
            draw_forest()
        
        return
  
  
    #---------------------------
    def move_rabbits():
    #---------------------------

        # retrieve the 'shared' lists defined above
        global positions_rabbits_x, positions_rabbits_y

        # move the rabbits (1.2 to the right and 1.6 upwards)
        rabbits_count = len(positions_rabbits_x)   
        for rabbit in range(rabbits_count):
            positions_rabbits_x[rabbit] = positions_rabbits_x[rabbit] + 0.6 
            positions_rabbits_y[rabbit] = positions_rabbits_y[rabbit] + 0.8 
    

    #--------------------------
    def draw_forest():
    #--------------------------

        # retrieve the 'shared' lists defined above
        global positions_rabbits_x, positions_rabbits_y

        # define the axes of the forest
        plt.axis([0, 100, 0, 100])

        # draw the rabbits (blue dot)
        plt.plot(positions_rabbits_x, positions_rabbits_y, 'o', color = 'blue', markersize = 6)   
        
        # update the frames (for a simple animation)
        plt.draw()        
        plt.pause(0.001)
        plt.show()
        plt.clf()
 

    #====================
    #== Main program ==
    #====================
    predator_prey()

The piece of code above consists of 3 functions:

   1. `predator_prey()`: defines the starting position of the rabbits, controls the simulation by taking steps in time (a second each) and calls for each step in the the functions `move_rabbits()` and `draw_forest()`. Is called as the 'main program' at the bottom of the code.
    
   2. `move_rabbits()`: changes the position of the rabbits

   3. `draw_forest()`:  displays the rabbits to the screen
 
<b>Extra piece of Python: global variables</b><br>
If a variable of list is used in multiple functions, it can be useful to declare that variable so-called 'globally'. All functions in the program can then declare to use those variables. In our piece of code there are two lists that we'd like to use in multiple functions: `positions_rabbits_x` and `positions_rabbits_y`. These lists are used in each of the three functions: the starting positions are defined in `predator_prey()`, they're changed in the `move_rabbits()` function and are used to display the rabbits locations in `draw_forest()`. The syntax to define global variables and use them is as follows: the lists are declared at the top of the file preceded by the word `global` and are then retrieved at the top of each function by once again preceding them by the word `global`.

If you want to use a variable in a single function and only there you should <b>not</b> declare it as a `global`.


## Assignment 1: modelling the movement of rabbits

In the example above we assumed that rabbits move 0.6 meters to the right and 0.8 meters upwards at every time interval (of a second). This is a far cry from a realistic system of course: rabbits do not move synchronously, they do not run in a straight line and if we we're to run the system for long enough they would happily run out of the forest. That is not the intention of this assignment. The rabbits each move their own way and if rabbits near the edge of the forest they'll quickly return to the relative safety of the forest. In this first assignment we'll introduce the code necessary to approach realistic rabbit behavior. Create a file called `predator_prey_1.py` and copy the above code into that file. Then follow the next part of the assignment.

<br>

#### Part (1a): new parametrization of the movement of rabbits

In the function `move_rabbits()` we now have the rabbits move to the right and up. We could also have implemented the movement of rabbits in a different way. For example by saying that rabbits all move with the same speed (1 meter per second) and that they, specifically for this example, also move with the same angle as opposed to the x-axis of about 51 degrees. For the rest of the assignment we'll indeed move with a universal rabbit speed, but we'll at least make sure each rabbit chooses their own direction.

Add to the main program a variable called `rabbit_speed` that contains the universal speed for all rabbits. Also add a list called `rabbits_angles` that holds the angle of each rabbit as opposed to the x-axis, with which they move in a specific direction. Because you use the new variables in two functions, specifically `predator_prey()` (choosing the initial values) and `move_rabbits()` (calculating new positions) it is useful to also declare these variables `global`ly. 

In `move_rabbits()` where you calculate the new positions of the rabbits, you'll have to first convert the speed and angle into speed along the x- and y-axis, so you can calculate the new values of its x- and y-coordinate. After all, their positions are stored as x and y values. For each rabbit we first:

{: .language-python}
       angle = rabbits_angles[rabbit]
       velocity_x = rabbit_speed * cos(angle)
       velocity_y = rabbit_speed * sin(angle)
    
Because our time steps are exactly 1 second we can then calculate the new positions as follows:

{: .language-python}
       positions_rabbits_x[rabbit] = positions_rabbits_x[rabbit] + velocity_x
       positions_rabbits_y[rabbit] = positions_rabbits_y[rabbit] + velocity_y

The code above actually read velocity_x * dt, but since the time steps (dt) are 1 second we can leave out that multiplication. This implementation allows us to give each rabbit a unique direction at the start of a simulation. Apply the above changes to your program, give each of the rabbits their own direction and run the simulation for 20 seconds instead of 10.

<b>Note:</b> to be able to use trigonometric functions in your code like this you first have to import the math library from Python: `from math import cos, sin`
<br>

#### Part (1b): the edge of the forest

Our rabbits, cowards that they are, will never leave the forest. As soon as they accidentally set foot outside the forest they turn around and make their way back where they came from into the forest. Adjust the function `move_rabbits()` in such a way that the rabbits will always remain inside the forest.

Utilize the following strategy when the rabbit has moved outside of the forest after a movement:

   1. take one step back (both x and y) so the rabbit is in its original position
   2. turn the rabbit around by changing the angle with which the rabbits moves into an angle exactly opposite the one they were taking: 'angle_new = angle + $$\pi$$'. Replace their direction with the new one in `rabbits_angles`. So that the rabbit runs back into the forest at the following time step.
   
Try this by moving one rabbit straight for the edge of the forest and see if they indeed properly 'bounce' back into the forest as soon as they pass the boundary.

<br>

#### Part (1c): random rabbit behavior

Everyone who owns a rabbit has seen them move and knows they do not move in a straight line, but instead freeze in place every now and then to then change direction. This is a characteristic we'll be implementing as well in our simulation. 

![](konijnen.gif){:.inline}{: style="width:30%"}

Edit the function `move_rabbits()` such that the rabbits will freeze in place on average once per 20 seconds and then continue moving in a random new direction. Practically this means that a rabbit has a 5% chance for each second to sit still and change direction and has a 95% chance to just continue along the same direction. A possible implementation of this behavior is by using a random number $$x$$ (between 0 and 1).

{: .language-python}
    x < 0.05 (5% chance): no move, but instead a new angle (0<angle<2*pi) 
    x > 0.05 (95% chance): regular move

<b>Note:</b> to generate a random number you need the random library. Make sure it's included in your code `import random`

<br>

#### Part (1d): simulation with 25 rabbits

A world with only two rabbits is not very realistic. Edit the start of `predator_prey()` so that it included 25 rabbits in the simulation. Make sure your code generates a random position for each of the rabbits, but not outside of the square described by $$20 < (x,y) > 30$$. Also assign each of the rabbits a random starting direction: $$0 < $$angle$$ > 2\pi$$.

<b>Note:</b> In the function `predator_prey()` you also have to add the parameters (x-position, y-position and angle) in the lists for each of rabbits. Make sure to declare them as 'empty' lists before populating them. So: `positions_rabbits_x = []` etc. This 'clean slate' is important when we run multiple simulations in succession. Which we want to do! 

<br>
