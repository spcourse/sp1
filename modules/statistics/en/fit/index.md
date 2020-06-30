## Assignment 4: A somewhat more complex model: f(x) = ax+b and fitting in Python itself

Someone in the research group has proposed that there might be a (linear) relation between the length of women and the income of their parents. This could have several causes, but we'll leave that for later. The first step in the research is to examine whether there is a relation at all. We're going to try and look for a relation in the data.

Fitting a straight line is only appropriate if there is no dependence between the variables. In most cases there is such a dependence: the height of the sea level as a function of the time (sinus), the decay of a radioactive element (exponential) or the velocity of planets as a function of their distance to the sun (inversely proportional to the root of the distance to the sun). In those cases we follow the same steps: vary the parameters until  $$\chi^2$$ is minimized. Fitting a model to measurements is a standard procedure that you'll often encounter as a scientist. Fitting is often necessary if you test a variety of hypotheses or try to discover the underlying dynamics. Implementing a fit in a model with multiple (correlated) parameters can quickly become very complex and costs a tremendous amount of computational power unless approached in a smart way. Just like any programming language, Python has libraries stocked full with functions that can help you with that. Although for this course we do not have the time to take an in-depth look at these functionalities and all details that accompany them, we do want to give an example so you know how fitting a model works in practice.

#### Fitting in Python: f(x) = C (1 degree of freedom)

    # import the module that contains the fit-tool
    from scipy.optimize import curve_fit

    # define our model. In our case a constant function: f(x) = a 
    def my_fit_function(x, a):
        return a

    # define data and errors
    data_x       = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    data_y       = [171.2, 169.1, 170.8, 169.4, 173, 171, 174, 174, 173, 176]
    data_y_error = [4, 4, 2, 2, 2, 2, 2, 2, 4, 4]
    
    popt, pcov = curve_fit(my_fit_function, data_x, data_y, None, data_y_error)
    print(f"Best value: f(x) = {popt[0]:5.2f}")

The final line is still a bit of magic, but `popt` is a list containing the 'optimal' parameters of the function that you fitted the data to. In our case that's only 1 parameter, because we maintain a constant function as our model. You can look through the documentation yourself about how to use `pcov` (the matrix of covariances) to determine the uncertainty.

#### Fitting in Python: f(x) = ax+ b (2 degrees of freedom)

If, instead of a constant function, you'd want to fit a linear function $$f(x) = ax+b$$ and you want to `print` the results, then you only have to adjust the code in 2 locations. The location where you define the function that you fit to and the location where you print the results to the screen. Go ahead an find them.

    # import the module that contains the fit-tool
    from scipy.optimize import curve_fit

    # define our model. In our case a constant function: f(x) = a * x + b 
    def my_fit_function(x, a, b):
        return a * x + b

    # define data and errors
    data_x       = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    data_y       = [171.2, 169.1, 170.8, 169.4, 173, 171, 174, 174, 173, 176]
    data_y_error = [4, 4, 2, 2, 2, 2, 2, 2, 4, 4]
    
    popt, pcov = curve_fit(my_fit_function, data_x, data_y, None, data_y_error)
    print(f"Best value: f(x) = {popt[0]:5.2f} * x + {popt[1]:5.2f}")

#### Assignment 4: a fit to the data with a model: f(x) = ax+b

Write a program `statistics_4.py` in which you fit the data (of women's length and parents' income) to both a straight line and a linear relationship. To this end, use the tools in Python like we've demonstrated above and reproduce the graphs that we've shown at the beginning of the module. That means you have to show both the data and both of the 'best' functions in the graph. Make sure that the values of the parameters are displayed. Also `print` the values by way of output:

{: .language-python}
    A fit of f(x)=c     gives the best value:   c = x.xx
    A fit of f(x)=ax+b  gives the best values:  a = x.xx    and b = x.xx
