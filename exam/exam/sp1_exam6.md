# Exam Scientific Programming 1

Date: December 20 2022

This is a digital exam. The exam consists of 4 assignments in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam6

# Rules

- Create one file for all your solutions called `sp1_exam6.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Jump

Your goal is to create a list of numbers following logic. It starts with a 1. Every following number is defined by the number before it. If the number before it is even, you increase by one, if it is odd, you double the number. So 1, 2, 3, 6, 7, .... Because, 1 is odd, so the next number is 1 * 2 = 2. 2 is even, so the next number is 2 + 1 = 3. 3 is odd, so the next number is 3 * 2 = 6...

Create a function `jump(n)` that generates the list op to `n` numbers. Have a look at the following example:

    jump_list = jump(4)
    print(jump_list)

    jump_list = jump(10)
    print(jump_list)

This should give the following output:

    # [1, 2, 3, 6]
    # [1, 2, 3, 6, 7, 14, 15, 30, 31, 62]

### Assignment 2: Short

It can be very tedious to summarize text in a useful way. So let's not do that. If we want to reduce a text by 25%, it's much easier to remove every 4th word. So, the sentence "I was offended by the suggestion that my baby brother was a jewel thief." Would become "I was offended the suggestion that baby brother was jewel thief.", removing "by", "my" and "a", being the 4th, 8th and 12th word respectively.

Write a function `silly_abridge(text, step)` that text, removes every `step`-th word and returns the result.

You don't have to worry about punctuation: if a word that you need to remove contains punctuation you can just remove that with the word.

Have a look at this example:

    alice = """Oh, how I wish I could shut up like a telescope! \
    I think I could, if only I knew how to begin."""
    silly = silly_abridge(alice, 4)
    print(silly)
    silly = silly_abridge(alice, 2)
    print(silly)

Expected output:

    Oh, how I I could shut like a telescope! think I could, only I knew to begin.
    Oh, I I shut like telescope! think could, only knew to

Tips:

- You can split a text into a list of words using the `text.split()` method.
- You can remove punctuation and space with the `text.strip(' .,!?;:')` method.

### Assignment 3: Longest sequence

Write a function called `longest_sequence(lst)` that takes a list (`lst`) as input and returns the *length* of the longest consecutive sequence of the same element.

Have a look at this example:

    longest1 = longest_sequence(['a', 'b', 'b', 0])
    longest2 = longest_sequence(['a', 'b', 'b', 0, 0, 0])
    longest3 = longest_sequence([1, 1, 1, 1, 2, 3])
    print(longest1)
    print(longest2)
    print(longest3)

Expected output:

    2
    3
    4

### Assignment 4: First dates

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

Write a function `dates_first_match_of_the_month(filename)`. That goes over all the matches and find the date of every first match of the month. It should return a list of those dates.

Example usage:

    dates = dates_first_match_of_the_month('barca.txt')
    print(dates)

Expected output:

    ['29/08/11', '10/09/11', '02/10/11', '06/11/11', '03/12/11', '08/01/12', '04/02/12', '03/03/12', '07/04/12', '02/05/12', '19/08/12', '02/09/12', '07/10/12', '03/11/12', '01/12/12', '06/01/13', '03/02/13', '02/03/13', '06/04/13', '05/05/13', '01/06/13', '18/08/13', '01/09/13', '05/10/13', '01/11/13', '01/12/13', '05/01/14', '01/02/14', '02/03/14', '05/04/14', '03/05/14']

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.

Example usage:

    dates = dates_first_match_of_the_month('barca_short.txt')
    print(dates)

Expected output:

    ['29/08/11', '10/09/11']
