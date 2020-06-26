# Student

When two students are drunk and lose each other from view it is unlikely they ever find each other again. Write a program that simulates the behavior of two drunk students.

![](AnimationRandomWalkDouble.gif)

## Specification

Write a program `student.py` in which you implement an animation of **two** students. Display on the screen how long the user of your program has to wait for it to finish.

## Analysis

A drunk student takes a step each second. The size of the step is the same each time ($$R = 1$$), but the direction in which he takes that step is completely random. Choose a random angle $$\alpha$$ for each step and determine the new $$x$$0position and $$y$$-position. This phenomenon is known as a *random walk*.

You could try and use pen and paper to give an indication about the average distance that the students will be removed from one another as a function of the time. You are not required to hand it in, but it could be useful to discus your plan of action with a fellow student.


## Hints

Start, simply, with an animation of a single student:

![](AnimationRandomWalk.gif)

## Tip

Save a video yourself? Use a tool such as [GifGrabber](http://www.gifgrabber.com) to create an animated gif. Which you can then watch in your web browser.

## Testing

This program is completely about the visual aspect and cannot be tested by `checkpy`. You have to have it signed by an Assistant during the practical.
