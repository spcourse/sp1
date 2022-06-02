# Exam Scientific Programming 1

Date: March 30 2022

This is a digital exam. The exam consists of 3 assignments in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam3

# Rules

- Create one file for all your solutions called `sp1_exam3.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Collatz

Write a function `collatz(number)`. This function should return the collatz sequence for the passed `number`. The Collatz sequence for a number is found by using the following steps:

- If the number is **odd** it should be multiplied by 3, after which 1 is added
- If the number is **even** it should be divided by 2

The Collatz sequence of a number will eventually return to 1, after which you can stop.

Example usage:

    print(collatz(3))
    print(collatz(16))

Expected output:

    [10, 5, 16, 8, 4, 2, 1]
    [8, 4, 2, 1]

Tip: To prevent your program from converting integers to floats, make sure to use integer division (`//`)!

### Assignment 2: Passwords

A website that you work for wants users to use more secure passwords. The passwords need to have at least 8 characters, never contain two of the same character directly after each other, and have at least one number. Write a function `check_passwords(passwords)`, that accepts a list of passwords and returns a list of booleans that indicate for each of the passwords if they meet the requirements listed above.

Example usage:

    passwords = ["secret", "strawberry", "sinkhole234", "1bigbeard", "butterknife", "abcdefg8", "aabbccdd18", "1two"]
    checked_passwords = check_passwords(passwords)
    print(checked_passwords)

Expected output:

    [False, False, True, True, False, True, False, False]


### Assignment 3: BTTS

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

Write a function `both_teams_to_score(filename)`. This function computes the percentage of matches where both teams scored and rounds it to two decimals.

Example usage:

    btts = both_teams_to_score('barca.txt')
    print(btts)

Expected output:

    0.57

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.

Example usage:

    btts = both_teams_to_score('barca_short.txt')
    print(btts)

Expected output:

    0.5

Tip: You can open and load files using: `with open(filename, 'r') as f:`
