# Exam Scientific Programming 1

Date: June 23 2022

This is a digital exam. The exam consists of 3 assignment in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides,,

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam4

# Rules

- Create one file for all your solutions called `sp1_exam4.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Fibonacci

The Fibonacci sequence is a sequence in which each number is the sum of the previous two numbers. The sequence starts with two 1's.
Write a function called `fibonacci(n)` that returns a list with the first n Fibonacci numbers.

Example usage:

    fibonacci_sequence = fibonacci(8)
    print(fibonacci)

 Expected output:

    [1, 1, 2, 3, 5, 8, 13, 21]

### Assignment 2: Count elements

Write a function `count_elements(text)` that counts how many elements someone is listing that start with a vowel (a, e, i, o, u). This function has `text` as input string in which elements from a category are listed separated by commas.
The output of the function should be the number of elements listed in the text.

Example usage:

    example_text = "Bananas, oranges, apples, strawberrys, grapes."
    print(count_elements(example_text))

 Expected output:

    2

Tip: you can split a text into a list of words using the `text.split()` method.
Tip: make sure that your function also works if an element starts with a character that is not in the alphabet and with both captial and small letters.


### Assignment 3: Shutouts

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

Write a function `shutouts(filename)`. That calculates how often Barcelona has won with a so-called shutout.
A shutout means that the opposing team has not scored during the entire game.

Example usage:

    wins = shutouts('barca.txt')
    print(wins)

Expected output:

    40

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.


Example usage:

    wins = shutouts('barca.txt')
    print(wins)

Expected output:

    2

Tips:

1. You can load files using: `input_file = open(filename, 'r')`
2. Don't forget to close the file: `input_file.close()`
