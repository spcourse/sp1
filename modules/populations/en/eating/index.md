
## Assignment 3: population dynamics (death - foxes eat rabbits)

In nature foxes and rabbits do not harmoniously live alongside each other. When a fox encounters a rabbit he'll eat said rabbit. Part of this assignment is study how long it take (on average) for the foxes to eat halve of the rabbits. We also study whether it is better for the rabbits to sit still occasionally or just run around continuously instead.

<b>Tip:</b> We'll now make an adjustment to the code you wrote for assignment 1 and 2. To make sure that the code from assignment 1 stays preserved we'll create a new file. Save your current code to a file called `predator_prey_2.py`. Afterwards create a new Python file, `predator_prey_3.py`, and copy all code you've written till now into the new file.

<br>

#### Part (3a): vanishing rabbits

The first part in this assignment is to simulate rabbits getting eaten when they come too close to a fox. Declare a new function `dinnertime()` that is called in the 'main function' `predator_prey()` after the move functions, `move_rabbits()` and `move_foxes()`. This function is tasked with evaluating, for each rabbit, whether they are too close to a fox. 'Too close' means: within 5 meters of the nearest fox. If so, the rabbit is eaten and it should be removed from the list of rabbits.

Use the following Python syntax to remove an element $$i$$ from a list $$example_list$$:

{: .language-python}   
     del example_list[i] 

<b>Note:</b> 
When you iterate over a list of 20 elements and remove element 10, all remaining elements after the removed element move over 1 position. Element 11 in the original list becomes element 10 in the new list etc. The list is also now only 19 elements large and if you eventually reach rabbit 20 it will no longer exist. A 'trick' to accommodate this effect is iterating the list from the back to the front. So you start at rabbit 20, and subsequently move over to rabbit 19 etc. The list might become shorter, but you'll never get into trouble because you won't remove an element you'll later want to inspect.

![](konijnenenvossenEtenstijd.gif){:.inline}{: style="width:30%"}

To iterate a list from the back to the front that is 20 rabbits large you can use the following syntax (rabbit counts from 19 through 0, try it out):

{: .language-python}   
    for rabbit in range(19,-1,-1):
         print(rabbit)         

Extra tip: when a rabbit is eaten remove the corresponding element from **all** lists, x-position, y-position and angles list included.

Add the finishing touches by `print`ing i to the screen at each time step and how many foxes and rabbits are still in the forest at that point in time.

<br>
          
#### Part (3b): Calculate the time at which the rabbit population is halved (+ plot)

When we run the simulation for a longer period of time we'll eventually reach a moment in time where the foxes have eaten half of all the rabbits. But how long does that take? That question will be answered in the following part of the assignment.

<b>Tip before we start:</b> Displaying the moving and disappearing rabbits to the screen is very time-consuming. When simulating 1000 time steps it works just fine, but when running longer or multiple simulations it is no longer practical. By doing away with the visualization you can win an enormous amount of time. Make sure you add a variable to your `predator_prey()` function that allows you to easily choose if you do or do not want to call the `draw_forest()` function. From now on we won't be running the visualization unless you want to yourself.
Visualizing still is more than 'just fun', it is incredibly important to simulations. It is a powerful tool to debug your code. Very handy, like you've more than likely already experienced earlier in the module, when you were implementing the edge of the forest or the `dinnertime()` function.


To calculate the time at which half of the rabbits were eaten, we'll edit two parts of the program:

   1. Let the simulation run for 1000 (simulated) seconds and keep track of the number of rabbits in a list for each time step within the `predator_prey()` function. Then `return` that list at the end of the function.
   
   2. Declare a new function `average_half_life()` that runs the `predator_prey()` function once. Because `predator_prey()` now returns the list containing the numbers of rabbits in each time step you can use it to calculate what the first moment is that only half the original amount of rabbits is left in the forest.
   

The time that foxes require to achieve that will be different for each separate simulation. Below you can see a couple of graphs of the number of rabbits as a function of the time for two simulations. Before we calculate the average time after which 50% of the rabbits has disappeared for 1000 unique simulations, it is important to know that the values that you find are correct. First try to reproduce these graphs to see whether you do indeed collect the correct data from you simulation.

 ![](halfwaarde3x.png){: style="width:65%"}

At the end of your simulation the following should be displayed on the screen:

{: .language-python}   
    After x.xx seconds more than half the rabbits have been eaten

<br>

#### Part (3c): Average amount of time after which the rabbit population is halved

Our new function `average_half_time()` is constructed so that the function `predator_prey()` is only called once. Which means only a single simulation is run each time. But like you've already seen there is a relatively large spread in half-life between different simulations. To determine the <b>average</b> half-life we'll need to run a large number simulations, determine the half-life of each simulation and finally use all numbers to calculate the average.

<b>Note:</b> The graphs of the number of rabbits as function of the time that we've created for the previous part of the assignment were created to see if your calculation of the half-life was correct. Now that we're sure about that we can leave the graph out of our output. Adjust the code so that the graph is only shown when we run `predator_prey()` once. for the rest of the assignment we'll look at values for multiple simulations at which point graphs no longer matter.

Adjust the function `average_half_life()` so that it not just calls `predator_prey()` once, but instead calls it a large number of times (500), stores each half-life and lastly calculates the average half-life. It takes quite a while, so make sure at every 25 simulations the program `print`s what simulation is being run.

The screen should show the following after the final simulation:
{: .language-python}   
    A simulated world with: N_rabbits=25 (v=1), N_fox=2 (v=2), N_simulations = 500:
        Average half-life of rabbits = x.xx seconds

<br>

#### Part (3d): Strategy rabbits: does it help to adjust our speed?

In the previous assignment we determined the average half-life of the rabbit population for a specific speed of the rabbits. The rabbits probably don't want to die and should figure something out. Point of discussion between the rabbits is whether they should just run around real fast or instead stay put hoping the foxes don't find them. It's up to us to find the rabbits' optimal strategy.

To answer this question we'll run the function `average_half_life()` with various speeds for the rabbits. You may adjust the value of `rabbits_speed` manually between runs in the `predator_prey()`. You may also just write down the results of each run. Try the following speeds for the rabbits: speeds of 0.0, 0.5, 1.0, 1.5, 2.0, 2.5 and even 5.0 meters per second and finally create a graph of the average half-life's as a function of the speed of the rabbits. What strategy is more beneficial to the rabbits, move slowly or rather move very fast?

`Print` the values you've found to the screen:
{: .language-python}   
    A simulated world with: N_rabbits=25, N_fox=2 (v=1), N_simulations = 500:
        Rabbit speed = 0.0 m/s -> Average half-life of rabbits = x.xx seconds
        Rabbit speed = 0.5 m/s -> Average half-life of rabbits = x.xx seconds
        Rabbit speed = 1.0 m/s -> Average half-life of rabbits = x.xx seconds
        ...     

<br>
