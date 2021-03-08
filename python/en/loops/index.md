# Loops

In a computer program you often encounter a (small) set of instructions that you want to execute multiple times. They way to do and steer that is by using loops. On this page we discuss the format and features of loops and we will also explore a few examples where loops can be very useful.

Please create a file called `practicing_loops.py` and use it to implement the various examples and exercises on this page.

## Loops to repeat instructions

![embed](https://api.eu.kaltura.com/p/120/sp/12000/embedIframeJs/uiconf_id/23449960/partner_id/120?iframeembed=true&playerId=kaltura_player&entry_id=0_fmqp79t8&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en_US&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[hotspots.plugin]=1&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=0_blg5ympd)

A `for`-loop is used when you want to repeat a set of instructions. For example, if you want to print the numbers from 1 to 10 on the screen you could do that with ten separate print-statements, but you could also use the following construction:

    for x in range(1, 11):
        print(f"x now has the value {x}")

This program has as output:

    x now has the value 1
    x now has the value 2
    x now has the value 3
    ...
    x now has the value 10

The loop starts by setting the value of `x` to 1 and then executing *all* instructions in the loop one by one. After that, `x` is assigned the value 2 and again all instructions are executed. In this simple program there is only a single instruction: print the value of `x`, but we can of course expand the number of instructions. The most important notion is that the program automatically changes the variable `x`.


![](Loopsexplanation.png){: style="max-width:500px;"}


There are a few important things to note:

-   **Note:** Python counts *up to* the last number in the function range(): range(1,11) runs from *up to and including* 10. This is a very common mistake to make when you begin programming in Python. It might feel unintuitive, but that's just the way it is.

-   In the above example we assigned the name 'x' to the variable, but we could of course have used a different name like 'number', 'i', 'counter' etc. You can use whatever you want.

-   With range you can also specify the step size. This is standard set to 1, but if you prefer to take steps of 10 you would use the following syntax:

         for x in range (1, 100, 10):

    Please try this yourself to make sure you understand what values `x` takes in this program.

## Types of loops

In Python, just like in almost every other programming language, there are two different constructions to loop over a variable: the **for-loop** and the **while-loop**.

A for-loop is used when you know beforehand how often you want to repeat the set of instructions. In cases where you do not know that in advance and want to evaluate at every step if you want to continuer not, you use the while-loop. In a while-loop, just like in the for-loop, all instructions are executed for a specific value of the variable. Ths difference is that each time the variable is changed, there is an evaluation wether or not to re-do the block again.

In most cases, `for` and `while` are interchangeable. This for-loop:

	    for x in range(100):
	        print(f"x now has the value {x}")

is equal to the following `while-loop`:

	    x = 0
	    while x < 100:
	        print(f"x now has the value {x}")
	        x = x + 1

The reason that the `for`-loop is more often used is that it is a bit more compact and also easier readable. However this can only be done is you know beforehand how often this needs to be executed. In other cases, and also with user input it can almost only be done with a while construction.

<!-- ![embed](https://player.vimeo.com/video/287247106) -->

## Computing things using loops

In the first example we had only a single instruction in the loop itself, 'print the value of x on the screen', but you could have multiple instructions for every value x takes.

<!-- ![embed](https://player.vimeo.com/video/287247088) -->

In the next example we add the value of x to another variable that we have set to zero at the beginning of the program. At the end of the program this variable contains the sum of the values from 1 to 10. Once we have that, it is easy to get the sum of numbers from 1 to 712643 rather than from 1 to 10 of course.

As soon as all instructions have been executed forthe highest value the variable x can take, the loop is 'finished' and the program continues with all instructions after the for-loop. In this case we have the program print the value of the sum of all numbers. Please pay close attention to the indentation/position of the last line.

    total = 0
    for x in range(1, 11):
        print(f"x now has the value {x}")
        total = total + x

    print(f"The sum of all numbers from 1 to 10 = {total}")

**Exercise 1:** Please change this program by including another print statement: `print(f"The sum of all numbers from 1 to {x} = {total}")`. Include this line beneath `total = total + x`, in such a way that it starts at the same position (the same level of indentation). Run the program and try to understand what happens. Problems with indentation are a very common mistake when using loops, so it is important to see these type of 'mistakes' so you can recognize them later.

**Exercise 2:** At this moment we use the numbers from 1 to 10. Please try to adapt the program in such a way that you define a new variable once at the beginning of the program (so not in the range() function) that holds the maximum number. Use this maximum number as the maximum value for the for-loop: `for x in range(1, maximum)`.

**Exercise 3:** Make a program that has the same functionality as the original example, but now use a while-loop instead of a for-loop.

**Exercise 4:** Use a while-loop to ensure that the program will print numbers greater than 10, but that it will stop if the sum of all numbers up to that point is bigger than 123. To help you, the expected output is provided:

	Value of sum_x: 0, value of x: 10
	Value of sum_x: 10, value of x: 11
	Value of sum_x: 21, value of x: 12
	Value of sum_x: 33, value of x: 13
	Value of sum_x: 46, value of x: 14
	Value of sum_x: 60, value of x: 15
	Value of sum_x: 75, value of x: 16
	Value of sum_x: 91, value of x: 17
	Value of sum_x: 108, value of x: 18
	End value of sum_x: 126, end value of x: 19

## Filtering using loops

<!-- ![embed](https://player.vimeo.com/video/287247135) -->

Within the set of instructions you can also use conditionals. For example, if you want the loop to go from 1 to 20, but want to only print the numbers that are larger than 15 or numbers if it is divisible by three you could use the following code:

    for number in range(1, 20):
        if number > 15:
		   print(f"This number is bigger than 15: {number}")
        if number % 3 == 0:
		   print(f"This number is exactly divisible by 3: {number}")

We already mentioned that you can decide on the name of the variable. And as you see, in the above exampe we have changed the name of our variable 'x' to 'number'.

**Exercise 5:** Try to adapt the above example in such a way that at the end of the loop, the program prints to the screen how many numbers were exactly divisible by 3. To do this you will have to define a so-called 'counter', a variable that is set to zero at the start of the program and that is incremented by 1 every time you encounter a number that is exactly divisible by 3. Also take some time to format the output to the screen and have your program print:

    From the numbers 1 to 20 there are ... numbers that are exactly divisible by 3.


## Loops in loops

In the examples we have looked at up to now we have only printed things and saved some variables. Nothing too complex. This is not always the case and loops are often used in more complex constructions.

It is also possible to make loops within loops, so-called 'nested loops'*. If you for example want to vary a specific variable `y` from 1 to 3 for every value the variable `x` takes (for example when `x` is the student number and `y` is the mark for three different assignments during an exam) you can use the following construction:

    for x in range(1, 6):
       for y in range(1, 4):
           print(f"x = {x}, y = {y}")

This program has as output:

    x = 1,  y = 1
    x = 1,  y = 2
    x = 1,  y = 3
    x = 2,  y = 1
    ...
    x = 6,  y = 2
    x = 6,  y = 3

**Exercise 6:** Adapt the program in such a way that the print-statement is only executed *if* the sum of `x` and `y` is more than 6.

**Exercise 7:** Adapt the program in such a way that the program, at the moment just before a new value is assigned to `x` (i.e. just after the loop over y is finished) the program prints: `The value of x is now ... and we have just finished the loop over y`.

The output should look as follows:

	x =  1,  y =  1
	x =  1,  y =  2
	x =  1,  y =  3
	The value of x is now 1, we have just finished the loop over y.
	x =  2,  y =  1
	x =  2,  y =  2
	x =  2,  y =  3
	The value of x is now 2, we have just finished the loop over y.
	...
	The value of x is now 5, we have just finished the loop over y.

**Exercise 8:** Adapt the program in such a way that `y` does not run from 1 to 4, but from 1 to the value of `x`.

**Exercise 9:** Adapt the program of exercise 8 to use a while-construction for the value of `y`. The for-loop for `x` stays the same.

**Exercise 10:** Adapt the original program in such a way that the loop over `y` is only executed *if* `x` is larger than 3. *Keep* the range(1,6) in the for-loop of `x` the same, using a conditional (an if-statement) as a solution.

Here's an example of what the output should be:

	x = 4, y = 1
	x = 4, y = 2
	x = 4, y = 3
	x = 5, y = 1
	x = 5, y = 2
	x = 5, y = 3

Could you get the same result by changing the range in the for-loop of `x`?

## Practice and  debugging

If you meet a for-loop somehwere in this course that you don't understand very well, either in the examples we give or in your own code, please come back to this page and read it again. Last tip: you can always use print-statements to verify if the loops are really doing what you think you have told them to do.
