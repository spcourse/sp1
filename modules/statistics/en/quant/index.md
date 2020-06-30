## Assignment: betas as bankers in the City (Quants)

At a lot of banks and insurance companies you'll find mathematicians and physicists in employment: in the so-called risk-analysis departments, but also as quantitative analysts: quants. Let's try that for ourselves by trying to predict the closing prices of the AEX in the year 2000 by using the years that came before: 1991-1999.

The closing prices of the AEX can be found at [AEX wiki](https://en.wikipedia.org/wiki/AEX_index):

![](AEXeindstandTabel.png)

### Bonus Assignment: predict the AEX closing prices in the year 2000 

Write a program called `statistics_bonus.py` in which you predict the closing prices of the AEX in the year 2000 based on the values at each end of the year closing values from 1991-1999. Follow these steps:

   1. Create a graph of the closing prices of the AEX as function of the year since 1991.

   2. Fit the measurements with a second degree polynomial: $$f(x)=ax^2+bx+c$$. 
      Adjust the fitting function to one what we've used before in this module.

As soon as you've found the function that correctly used the data points, you have a model with which you can extrapolate. What is your prediction of the closing prices of the AEX in the year 2000? Cross reference these with the actual value that was realized (637,60). And? How's that possible?
    
    
	