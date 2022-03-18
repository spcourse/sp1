# Practice exam Scientific Programming 1

This is a digital exam. The exam consists of 3 assignment in which you have to write a shor python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides,,

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam1

# Regels

- Create one file for all your solutions called `sp1_exam1.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` oor any other external Python module.
- You're only allowed to use the website progbg.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Fizzy

Write a function called `fizzy(n)`. This function returns a list with all _fizzy_ numbers between `1` and `n` (including 1, excluding `n` itself). We define a _fizzy_ number as a number that is divisible by 3 and 5 or divisible by 3 and 7 (or both).

Example usage:

    fizzy_list = fizzy(100)
    print(fizzy_list)

Expected output:

    [15, 21, 30, 42, 45, 60, 63, 75, 84, 90]

Tip: you can use the `%`-operator to test for divisibility.

### Assignment 2: Starting letter

Write a function `filter_words_starting_with(text, letter)`. This function has two input strings: `text` and `letter`. The function finds all words from `text` that start with `letter` and it returns those words in a list. You may assume that the string `letter` indeed always contains a single letter.

Example usage:

    example_text = "David Donald Doo dreamed a dozen doughnuts and a duck-dog, too."
    print(filter_words_starting_with(example_text, "d"))

Expected output:

    ['David', 'Donald', 'Doo', 'dreamed', 'dozen', 'doughnuts', 'duck-dog']


### Assignment 3: Winning streak

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

Write a function `longest_streak(filename)`. This function computes the length of the longest winning streak.
A winning streak is a period of consecutive wins (so uninterrupted by any losses or draws).

Example usage:

    streak = longest_streak('barca.txt')
    print(streak)

Expected output:

    13

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.


Example usage:

    streak = longest_streak('barca_short.txt')
    print(streak)

Expected output:

    1

Tips:

1. You can load files using: `input_file = open(filename, 'r')`
2. Don't forget to close the file: `input_file.close()`
