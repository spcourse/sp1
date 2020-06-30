## Assignment 2: Harsh reality for the rabbits: foxes

Sure, you can watch an entire afternoon at 25 rabbits running around an imaginary forest, but there's nothing particularly exciting of complicated about that. Let's add some spectacle. 

<br>

#### Part (2a): introduction of foxes

Besides rabbits, also foxes live in the forest. Adjust the code you've written earlier so that there's also (two) foxes present in the simulation and on your screen. You can broadly use the same structure that we've also used for the rabbits. First, create the lists that store the positions and directions of the foxes and then create a new function `move_foxes()`, that moves the foxes each step. Call that function in `predator_prey()` too, just below `move_rabbits()`. Just like the rabbits, the foxes will never leave the forest. So make sure to implement the same feature that keeps the rabbits within the forest for the foxes. Finally you'll also have to adjust the `draw_forest()` function to also display the foxes in the animation.

There are a couple of differences between foxes an rabbits:

   * foxes are twice as fast as rabbits (`fox_speed = 2`) and they never stop moving
   * draw foxes in red (`size = 10` instead of `size = 6` for rabbits)

Let the foxes start at positions (70, 70) and (80, 80) and at the start have fox 1 move to the left and fox 2 to the right.

<br>

#### Part (2b): specific movement behavior of foxes

![](konijnenenvossen.gif){:.inline}{: style="width:30%"}


Just like the rabbits, foxes have a unique way of moving. The fox has a tendency to move straight ahead, but can decide to veer to the right or left after each step. The chances of a specific change in angle as opposed the original direction strongly diminishes the greater the deviation is. The distribution of chances follows a so-called normal distribution. Like this, the fox always follows a sort of pseudo-random walk that has a strong preference for moving in the original direction. Implement this behavior in your simulation.

<b>Python input:</b> To generate a 'random' new direction from a normal distribution you need a function that is found in the numpy library. Include it in you code: `import numpy as np` and use the following syntax to generate a random number centered along the original direction:


{: .language-python}   
     angle_new = np.random.normal(foxes_angles[fox], 0.2)  

Let the fox first take a step and only then calculate a new random direction, which you can store in `foxes_angles`. During the next step the fox will move in the new direction. The value 0.2 in the above expression is the so-called width of the normal distribution. It decides how easy (or difficult) it is for the fox to move away from their original direction.

<br>

