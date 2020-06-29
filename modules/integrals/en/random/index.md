# Interesting fact on the sum of random numbers

Write a function that determines the average number of random numbers (uniformly distributed between 0 and 1) that need to be generated for the sum of those numbers to be greater than 1.00.

Use the following strategy:

*   Generate random numbers until the sum is larger than 1. Use a `while` loop to achieve this

*   Repeat this a large number of times (N = million)

*   Determine the average number of required numbers and display that count

### Specification

*   Create a new file called `randommaths.py`.

*   Declare a function called `random_maths()` that takes no parameters and which determines the average number of random numbers that need to be generated for the sum of those numbers to be greater than 1.00.

*   The output on the screen (4 decimals precise) should look like this:

		The average amount of numbers generated (based on 1 million trials) is: x.xxxx

### Testing

	checkpy randommaths.py


### Acknowledgements

Source: @fermatslibrary.
