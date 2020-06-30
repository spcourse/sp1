# Statistics #

A subject that connects students of different educations is the fear for (the shortage of knowledge about) statistics. And yet it is a crucial part in every scientific discipline, because it is the key to drawing conclusions from collected data. What is the 'truth' that is hidden inside data and how can we weigh different hypotheses against one another? In this module we'll take a look at some of the most well-known techniques by using a fabricated case and made up data.

![](ExampleDenemarken.png){:.inline}{: style="width:35%"}

**The case:** In Denmark there is a group of researchers that studies whether the length of women is correlated to the income of their parents. The categories of income vary from category-0 (very poor) to category-10 (very rich) and from each category a random number of women have been selected and their length was measured. The data (the average measured length for each category of income) is represented in the graph to the side. This is where the trouble begins. A part of the researchers thinks the data suggests that there is a linear relationship (blue) whilst another group thinks there's no relationship whatsoever (red). The latter group says the observed 'light' dependence is just the result of accidental fluctuations in length of the women that were sampled.

In this module, after first trying out some introductory exercises, we'll try to find out what conclusions can be drawn: is there, or isn't there a (causal) relationship?

Although it is not the goal to provide an entire lecture on statistics, we introduce here at least some statistics alongside the new Python ingredients as a preparation to the assignments.
 
## Assignment 1: percentage of women taller than an average man

In the first assignment we'll answer the question about what percentage of the women in the Netherlands are taller than the average man. For this assignment the concept of a normal distribution and how to manipulate it in Python is important.

#### Statistics info for assignment 1:  the normal distribution 

In nature variation is abundant: the length of people in a country, or the weight of animals in a population just to name a few. The distribution that describes the relative frequency of the occurrence of a specific value $$x$$ in the population of measurements is expressed by the so-called normal distribution:

$$ f(x,|\mu,\sigma) = \frac{1}{\sigma\sqrt{2\pi}} exp^{-\frac{1}{2}\left( \frac{x-\mu}{\sigma} \right)^2}$$

![](ExampleLengte.png){:.inline}{: style="width:35%"}

This distribution, also known as the Gaussian distribution, is characterized by only two parameters: the average ($$\mu$$) and the measure of spread ($$\sigma$$). About 68% (95%) of the values can be found within the area $$\mu \pm 1\sigma$$ ($$\mu \pm 2\sigma$$).

The length of men (women) in the Netherlands, for example, is described by a normal distribution with an average $$\mu$$ = 184.0 (170.6) cm and spread $$\sigma$$ = 7.0 (6.5) cm. This means that 34% of the men is taller than 191 cm and that 2.5% of the women is shorter than 157.6 cm. The (normalized) graphs of the two distributions can be seen in the graph on the side.

<br>

#### Python info for assignment 1: random numbers from a normal distribution

Earlier, we saw how to generate a random number in Python between 0 and 1. It is also possible to generate a random number from a specific distribution. Because the normal distribution is such a prominent distribution Python has a standard function implemented (in the `numpy` library) with the following syntax:

{: .language-python}
    average = 170.6
    spread = 6.5
    length = numpy.random.normal(average, spread)

When you create the variable length many times the values of $$length$$ will be distributed along the red graph above.

#### Assignment 1: distribution of lengths of all women

Create a program `statistics_1.py` in which you generate 1 million random numbers from the normal distribution that describe the length of women in the Netherlands. Create a graph of all these random lengths. Use a histogram for the graph with bins that are 0.5 cm large. While generating random lengths, keep track of how many women have a length greater than that of the average man. `Print` at the end of the program what the percentage tall women is, with a precision of 2 decimals.

{: .language-python}
    The percentage tall women (taller than 184 cm) is X.XX percent
