# Exam Scientific Programming 1

Date: March 30 2022

This is a digital exam. The exam consists of 3 assignment in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam2

# Rules

- Create one file for all your solutions called `sp1_exam2.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Distance

We have a list of successive distances from a trip and we would like to compute the cumulative distances from the start.
Write a function called `cumulative(distances)`. This function takes a list of distances and returns a list with cumulative distances (i.e., the distances summed from the start up to that point).

Example usage:

    distances = [2, 2, 1]
    cumulative_distances = cumulative(distances)
    print(cumulative_distances)

Expected output:

    [2, 4, 5]

Example usage:

    distances = [19, 32, 7, 1, 5, 1]
    cumulative_distances = cumulative(distances)
    print(cumulative_distances)

Expected output:

    [19, 51, 58, 59, 64, 65]


### Assignment 2: Longest word

Write a function `longest_word_length(text)`. This function finds the length of the longest word in `text`

Example usage:

    example_text = "The word 'antidisestablishmentarianism' is hated by people suffering from hippopotomonstrosesquippedaliophobia."
    print(longest_word_length(example_text))

Expected output:

    36

Example usage:

    example_text = "The word 'longer', is not the longest in this sentence."
    print(longest_word_length(example_text))

Expected output:

    8

Tip: You can split a text into a list of words using the `text.split()` method.

### Assignment 3: Home

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

Playing at home is considered an advantage for any football club. Let's see if this is true for Barcelona.
Write a function `home_advantage(filename)`. This function computes the difference between the amount of home matches won and the amount of away matches won. (So, a positive number means that more home matches were won than away matches.)

Example usage:

    advantage = home_advantage('barca.txt')
    print(advantage)

Expected output:

    15

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.

Example usage:

    advantage = home_advantage('barca_short.txt')
    print(advantage)

Expected output:

    2

Tips:

1. You can load files using: `input_file = open(filename, 'r')`
2. Don't forget to close the file: `input_file.close()`
