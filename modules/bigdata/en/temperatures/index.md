# Climate debate

![](../../assets/KaartNederlandKlein.png){:.inline}

Let's do our part for the climate discussion and analyze the data provided by the ECA (European Climate Assessment) [available](http://eca.knmi.nl/dailydata/predefinedseries.php) in big data files. We'll limit ourselves to the data pertaining to the maximum and minimum temperatures for each day measured in De Bilt since 1901.

Files: 

- [DeBiltTempMaxOLD.txt](../../data/DeBiltTempMaxOLD.txt)
- [DeBiltTempMinOLD.txt](../../data/DeBiltTempMinOLD.txt)

Download the files, open them and read the headers (at the top of the file) on how the data has been formatted. We can see the maximum (minimum) temperature at January 1st 1901 was -3.1 (-6.8) degrees Celsius.

> Note! The data files also contain all sorts of clarification. You're supposed to leave that in the file (don't change the contents of the file). Your Python program should be implemented in such a way that it skips those lines when it processes the file. Also, do not change the file names. 

Create a program **temperature.py** that parses the file line by line and answers the following questions.

### Assignment 1: extreme temperatures

What were the highest and lowest temperature that were measured in De Bilt since the start of the 20st century? What days were they measured? Make sure your program `print`s the dates properly to the screen. Don't say:

     Max 34.5 at 19670513

but      

     The highest temperature was 34.5 degrees Celsius and was measured at 13 may 1967.

Tip: make a separate function that takes a number like `19670513` and converts it into a more readable expression like `13 may 1967`.

### Assignment 2: cold colder coldest

What is the longest period of uninterrupted days that had freezing temperatures (maximum temperature below 0◦C)? What was the date of the last day of this period of time?

### Assignment 3: Summer days and tropical days

A day is a summer day when the maximum temperature is 25 degrees Celsius or higher. On a tropical day that maximum temperature would even reach 30 degrees. Make a graph where both the number of summer days and tropical days is displayed for each year.  

### Assignment 4: First heat wave

In the Netherlands we speak of a heat wave when the maximum temperature has been higher than 25◦C (summer days) for at least five uninterrupted days of which at least three days had maximum temperatures of at least 30◦C. `Print` the *first* year that a heatwave was found within the data set following this definition.

### Clean code and clean output

Make sure the code of all your assignments is written in one or more functions. Do not use global variables (ask an assistant if this is not clear)!

You can see above that there are a couple of statements that need to be `print`ed and one graph has to be created. Make sure the requested information is `print`ed on separate lines, in the correct order.

## Testing

Now you're ready to test with checkpy:

    checkpy temperature


