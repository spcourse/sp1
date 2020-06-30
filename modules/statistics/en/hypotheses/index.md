
## Assignment 5: Testing hypotheses

Part of the researchers think the data suggests there is a linear relationship within the data. Another part of the researchers think there is no dependence and that the observed (small) dependencies are just a coincidence caused by the specific samples that were collected. We'll conclude this module by supplying quantitative data to this ongoing discussion.

The question really is: "How rare is the case that, given that there is <b>no</b> actual relationship, a series of samples (of this size in each category) produces a slope that is of equal value or even larger than found in the data?". The probability at which this occurs is often encountered in literature and is also known as the <font color = 'red'> p-value </font>.

#### Assignment 5: Simulate random data-sets and calculate the p-value

Write a program `statistics_5.py` that answers the question above by examining how rare it is that the observed slope is present within the data, when in real life there is no dependence at all.

To answer this question, apply the following strategy:

   1. Simulate a data-set:

      * Work by the assumption of a 'flat' hypothesis: f(x) = C, where C has the same value as in assignment 3.

      * Choose from each of the 10 income categories a 'random' measurement by using the `np.random.normal(average, spread)` function, where the average in each category is given by the value that you found in assignment 3. For the spread in each category you should use the uncertainty of the average length in that specific category from the original data-set. For example, an uncertainty of 4 cm in the income category 1.
	
      * Assign the same error as in the original data to the uncertainty of the random chosen average length in each category. For example, 2 cm in income category 5.
	   
   2. Fit a function of the form f(x) = ax+b and determine the slope (a) for the data-set created in 1.

   3. Repeat the above steps a large number of times (10000 times for example) and remember for each of the data sets what the slope was. Keep track of what fraction of the simulated data sets (coincidentally) had a slope equal (or greater than) that of the original data set (see assignment 4).

   4. Create a graph (histogram, see below) of all slopes and clearly display the values you've found in the data and the corresponding p-value.
	  
      ![](ExamplePvalue.png){: style="width:60%"}

   5. `Print` the p-value to the screen at the end of the program: in percentages, 2 decimal accurate.
    
      {: .language-python}
         The p-value for the alternative hypothesis: x.xx percent


In general we follow the rule that if the p-value is smaller than 5% we speak of a 'coincidence'. If the p-value is larger than 5% then we conclude that the observed trend is not described by the flat hypothesis and that we've found evidence for a relation.

*Note:* If you find a relationship it doesn't immeditaly mean you have found a causal relationship. Imagine that a relation is found (and always keep in mind that the observed effect can still be coincidental), what could the underlying cause possibly be? Richer people: eat healthier, live in houses in neighborhoods with better air quality, or the reverse that in our society the length might cause a higher income? Dig dig dig until you've dug to the core and find something new that no one has ever seen. That is science!


