# Algorithms

Computers truly shine when the solution to a problem cannot (or is hard to) be expressed by a formula. Programmers work to devise and implement *algorithms*, that exactly specify the step-by-step plan to solve a problem. An important aspect of algorithms is that they have to work for different inputs. In the video below the algorithm has to find the correct solution if there are 0, 1, 2, 3, 4, or more people in the room.

![embed](https://www.youtube.com/embed/6hfOvs8pY1k)

In the chapter [basics](/python/basics) you've learned a number of **instructions** that can be used in Python:

- the `print`-instruction, to display messages to the user
- the `input`-instruction, to process information from the user
- the `=`-operator, to define and manipulate variables

Aside from that, you've gotten acquainted with operators that are used to comprise expressions. This was already enough to write a functional program. Now we're going to make things more interesting by introducing exceptions and repetition.

## Conditional Instructions

The preceding programs were scripts that were meant to be executed line for line from top to bottom. A sort of step by step guide. Programs get more interesting when we intend to write *exceptions*.

In Dutch, we introduce `if`-statements with a couple of examples:

![embed](https://player.vimeo.com/video/287244672)

In English, read a bit more about [conditionals](http://greenteapress.com/thinkpython/html/thinkpython006.html) at Think Python.

## Details

An `if`-statement in Python is structured as follows:

    balance = 100
    expense = 75
    if balance - expense > 0:
        balance = balance - expense
        print("Transaction complete.")
    print(f"Your balance is {balance}.")


A **condition** ultimately only has two possible outcomes. In Python these are `True` and `False` (these are called **boolean** values, after [George Boole](https://en.wikipedia.org/wiki/Boolean_algebra#Values)). In the code shown above the this boolean is the result of the expression `balance - expense > 0`. In this case the comparison operator `>` ('greater than') is used. This operator compares two parts, the first part is the result of `balance - expense` and the second part is `0`T. After which the result is evaluated into a boolean. Depending on the result, a `True` or `False` , the code within the if-statement is executed (the result was `True`) or skipped entirely (the result was `False`).

The `:` on the same line as the `if` signals that there's a **code block** that accompanies the `if`-statement. That's the particular part of code that is only executed if the condition is met. Such a block of code consists of multiple lines of code which are **indented** a set amount. Indenting code means you precede the lines with a certain amount of spaces or tabs. In the code above a number of 4 spaces is used to indicate which lines of code are associated with the `if`-statement. Since the second `print`-statement is not indented, it is no longer part of the previous code block and is therefore not dependent on the condition of the `if`-statement. It is executed *unconditionally*.

## More operators

Should you need more than the comparison operator:

- `==`  equal (note: a single `=` is used for assigning, double `=` is used for comparing!)
- `!=`  unequal
- `>` 	greater than
- `>=`	greater than or equal
- `<` 	smaller than
- `<=`	smaller than or equal

## Combining conditions

You can also combine multiple conditions. If you want to know whether a number is situated within a certain range (for example between 3 and 39), then you do so with the `and` operator:

    x = 15
    x_min = 3
    x_max = 39
    if x > x_min and x < x_max:
        print(f"the number {x} lies between {x_min} and {x_max}")

The following three operators are all operators you need to combine multiple conditions:

- `not` negation
- `and` combination (both must be `True` to be `True` together)
- `or` combination (either or both must be `True` to be `True` together)

## Loops

Occasionally it is useful to determine whether a whole sequence of numbers meets a certain condition. In that case, we would like to repeat a piece of code for all numbers in that sequence. Repetition, such a "simple task", is exactly the strong suit of a computer and has become a basic element in virtually all programming languages. We call this a **loop**.

## Repetition

If we want to repeat something for 10 times, it would look like this:

    for x in range(1, 11):
        print("hello")

We use the command `range()` with a start and an end to indicate how many times the loop should repeat. A Python `range` runs from the start *up to* the end, so it is not *inclusive*!

Aside from that, just as with the `if`-statement, the `for` ends with a `:`, to indicate which *lines* of code should be repeated. Which in this case would only be the `print` that is preceded by 4 spaces.

## Examples of loops

In Dutch:

![embed](https://vimeo.com/album/5380755/embed)

In English, read more about [iteration](http://greenteapress.com/thinkpython/html/thinkpython008.html) at Think Python.

## Step size of a loop

You can also declare the step size for a `range`. The range still runs from start up to the end, but instead of steps of 1, it will take steps the size that you've set. Like this:

    for number in range(1, 100, 10):
        ...

Each step in the `for`-loop will be 10 larger than the previous. Take a minute to think over the steps the above loop would make; or copy the code and add a `print` to it to study its behavior.

## Types of loops

Dependent on the type of application you can choose either type of loop that you've seen in the videos before. The `for` and `while` are practically interchangeable. This `for`-loop:

    for i in range(100):
        print("hi")

does the same as the following `while`-loop:

    i = 0
    while i < 100:
        print("hi")
        i = i + 1

Obviously, the `for`-loop is somewhat more compact and more readable. Therefore, this type of loop is used most often. Cases such as asking for user input are often times best implemented with a `while`-loop. As a general rule for which loop to choose; a `for`-loop is used if you know, or can calculate, exactly how often the loop should repeat. A `while`-loop is used when the amount of repetitions is uncertain.
