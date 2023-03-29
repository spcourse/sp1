# Exam Scientific Programming 1

Date: March 29 2023

This is a digital exam. The exam consists of 4 assignments in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam7

# Rules

- Create one file for all your solutions called `sp1_exam7.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Jump

Write a function `integer_sequence(n)` that takes a positive integer $$n$$ as input and generates a sequence of numbers as follows:

1. If $$n$$ is even, add $$2$$ to it.
2. If $$n$$ is odd, subtract $$1$$ from it.
3. Divide the result of step 1 or 2 by $$2$$.
4. Repeat steps 1-3 until $$n$$ becomes $$1$$.

The input number, $$n$$, and the final number, $$1$$, are also part of the sequence. The function should return the result of this sequence.

Example usage:

    print(integer_sequence(10))
    print(integer_sequence(12))

Expected output:

    [10, 6, 4, 3, 1]
    [12, 7, 3, 1]

### Assignment 2: Sam-I-am

There is some debate if you should put one or two spaces after a sentence. Let's say we prefer single spaces. Write a function `single_space(text)`, that takes a text as input and removes any double spaces. The result should be returned as a string. You may assume that the text never contains more than two consecutive spaces.

Example usage:

    sam = "I am Sam.  I am Sam.  Sam I am.  That Sam-I-Am!  That Sam-I-Am!  I do not like that Sam-I-Am! Do would you like green eggs and ham?  I do not like them, Sam-I-Am.  I do not like green eggs and ham."
    print(single_space(sam))

Expected output:

    I am Sam. I am Sam. Sam I am. That Sam-I-Am! That Sam-I-Am! I do not like that Sam-I-Am! Do would you like green eggs and ham? I do not like them, Sam-I-Am. I do not like green eggs and ham.

### Assignement 3: Fibonacci

A Fibonacci number is a sequence of numbers in which each number is the sum of the two preceding numbers, starting from 0 and 1. In mathematical terms, the Fibonacci sequence can be defined as follows:

$$
F_0 = 0
F_1 = 1
F_n = F_{n-1} + F_{n-2} \textrm{, for } n > 1
$$

So the first few numbers in the sequence are:

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...

Where the 0st fibbonacci number is 0, the 1st fibbonacci number is 1, the 2nd fibbonacci number is 1, the 3d fibbonacci number is 2, etc.

Write a function `fibonacci(n)` that computes the `n`th fibonacci number.

Example usage:

    print(fibonacci(4))
    print(fibonacci(10))

Expected output:

    3
    55

### Assignments 4: Goals per year

For this assignment you need to use the file [barca.txt](barca.txt). This contains the results for football matches of F.C. Barcelona (from seasons 11/12 to 13/14). The file contains the following data:

    29/08/11,Villarreal,won,5,0,home
    10/09/11,Sociedad,draw,2,2,away
    17/09/11,Osasuna,won,8,0,home
    ...
    03/05/14,Getafe,draw,2,2,home
    11/05/14,Elche,draw,0,0,away
    17/05/14,Ath Madrid,draw,1,1,home

As you can see, the data fields are separated by a comma and contain the following information:

1. Date of the match
2. The opponent
3. The result: won/lost/draw
4. The number of goals for Barcelona
5. The number of goals for the opponent
6. The location: away/home

Write a function `total_goals_per_year(filename)`. That goes over all the matches and computes the total number of goals _that Barca scored_ _for each year_. The result should be a list conataining a total for each year in the dataset. The file `barca.txt` contains the results for 4 consecutive years, so the result should be a list containing 4 numbers (the total Barca goals per year). The total goals fo the first year (2011) is 50, so the first element of the list should be 50.

Example usage:

    dates = total_goals_per_year('barca.txt')
    print(dates)

    dates = total_goals_per_year('barca_short.txt')
    print(dates)

Expected output:

    [50, 121, 107, 51]
    [17]
