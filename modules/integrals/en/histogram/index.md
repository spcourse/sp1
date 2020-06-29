# Histogram

Write a program that visualizes the distribution of numbers from the `random`-function:

![](HistogramExample.png)


## Background

Plotting a graph of a function, like in the last module, is one of the many ways of visualizing data. This is not always the most obvious strategy however. When the Volkskrant, for example, makes a graph of how tall the Dutch people are, they use a so-called `histogram` (also known as a bar chart or frequency distribution) in which the data gets grouped together. People, for instance, would be grouped together in percentages of people with lengths ranging from 165-170, 170-175 and so on. The way to represent data also gives some insight in how different groups relate.


## Example: 10.000 random numbers

The idea of generating random numbers is that the random numbers are uniformly distributed between 0 and 1. To get an impression of whether the distribution really is 'flat' we could generate 10.000 random numbers and check each unique numbers' frequency.

Below you'll find a small program that generates 10.000 random numbers and stores each random number in a list. When the command `plt.hist()` is given, we specify that we'd like to see the frequency of numbers in ranges of 0.02 (50 bins between the minimum expected value of 0.00 and maximum expected value of 1.00).

    import random
    import matplotlib.pyplot as plt
    
    # list of random numbers
    random_numbers = []
    
    # generate 10.000 random numbers
    n = 10000
    for counter in range(n):
        number = random.random()          
        random_numbers.append(number)
    
     # plot the frequency distribution (50 bins)
     plt.xlim(-0.1, 1.1)
     plt.hist(random_numbers, bins=50)
     plt.show()

In Python you can use the option `plt.hist()` to group data before showing it with `plt.show()`. When grouping data together, give some thought to how many bins you want to use to divide your data.

The extra option `xlim` is used to show that no numbers are generated outside of the interval 0.00-1.00. Look up the documentation on the web which options are available to design a histogram that are relevant to you: number of bins, color, axis labels, legend, text and much more.

## Assignment: distribution of the sum of random numbers

We've now seen that random numbers are properly generated uniformly between 0 and 1, but what about the distribution of the sum of 100 random numbers? When we do an 'experiment' in which we take the sum of 100 random numbers, the average of that sum would be 50 (since the average number is 0.5). But for an individual experiment it is rarely exactly 50. That leaves the question: how often is the sum less than 40? And is that just as likely as a sum of greater than 60?

Write a function `sum_random_numbers()` that displays the distribution of the sum of 100 random numbers from 10.000 experiments. Graph the results between x = 30 and x = 70.

Generate for each 'experiment' 100 random numbers and calculate the sum of those numbers. Repeat this 10.000 times and store for each of the experiments the sum in a list. In the end plot those values in a frequency distribution (histogram). Also `print` to the screen the percentage of the experiments in which the sum was respectively less than 40 and more than 60.

> Note: `print` the percentage < 40 on one line and the percentage > 60 on the next line. `Print` not only the percentage but also explain exactly what kind of number it is.


## Testing

	checkpy histogram
