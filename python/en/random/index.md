# Random numbers

A very useful building block in your computer is the *random* number. In the library `random` you can find a function called `random()` that generates a random number between 0 and 1. In python you can use the function as follows:

    import random
    x = random.random()
    print(x)

Every time you call the function it will generate a new number. To generate ten random numbers you'd have to run the following:

    import random
    for i in range(0, 10):
        x = random.random()
        print(x)

> Try the above mentioned programs for yourself as well! Do watch out that you do not call the file `random.py` though. In that case `import random` will try to import that local file instead of the Python library, which obviously will not work.

## Building with building blocks

As soon as you have a building block, you can build different objects with the aid of logic and mathematical manipulations. If you know that the function `random.random()` generates a number between 0 and 1 then you can think of a transformation which results in a number of, for example, between 0 and 3.

Example: ten random numbers between 0 and 3 

    import random
    for i in range(10):
        random_number = random.random()
        transformed_number = 3 * random_number
        print(y)

## Your own function

Write by way of practice, a function called `random_range()` that generates a number between *a* and *b* where you can choose the values a and b yourself. It has to in the following way:

    import random
    
    def random_range(a,b):
        random_number = <your code>
        return random_number
    
    minimum = 2
    maximum = 5
    for i in range(10):
        x = random_range(minimum, maximum)
        print(x)

Test your program by running it yourself and verify if each number lies in the correct range.
