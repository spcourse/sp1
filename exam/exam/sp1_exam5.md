# Exam Scientific Programming 1

Date: October 24 2022

This is a digital exam. The exam consists of 4 assignment in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam5

# Rules

- Create one file for all your solutions called `sp1_exam5.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Twoish


Write a function called `twoish(n)`. The functions approximates the number two by calculating the sequence $$1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \ldots$$ repeated $$n$$ times. So we compute the sum for $$\frac{1}{x}$$ where $x$ starts at 1 and is doubled at every iteration.

Example usage:

    almost_two = twoish(10)
    print(almost_two)
    less_two = twoish(2)
    print(less_two)

Expected output:

    1.998046875
    1.5

### Assignment 2: Hamming

Hamming distance is a metric used to compare texts. Normally you compare texts per letter, but we're going to compare them per word. You look at the individual words of both texts. You compare the first word of each texts. If they're the same, you count 1 point. If they're different you count 0. You do the same for the second word of each string, then the third, etc. The hamming distance is simply all points added up.

Write a function called `hamming_distance(text1, text2)` that compares two texts this way. Bear in mind some edge cases:

- If two texts have a different amount of words, you limit the comparison to the shortest of the two lengths.
- The function should not be case sensitive and not sensitive to punctuation.

Example usage:

    pretty_text = hamming_distance("Norwegian Wood", "Norwegian Fjord")
    print(pretty_text)
    pretty_text = hamming_distance("I love deadlines. I love the whooshing noise they make as they go by.",
                                   "I LOVE pizza. I love the round shape they have.")
    print(pretty_text)

 Expected output:

    1
    6

Tips:

- You can split a text into a list of words using the `text.split()` method.
- You can remove punctuation and space with the `text.strip(' .,!?;:')` method.

### Assignment 3: Populations

Say we have a population of n llamas. Each year, n / 3 new llamas are born, and n / 4 llamas pass away.

For example, if we were to start with n = 1200 llamas, then in the first year, 1200 / 3 = 400 new llamas would be born and 1200 / 4 = 300 llamas would pass away. At the end of that year, we would have 1200 + 400 - 300 = 1300 llamas.

To try another example, if we were to start with n = 1000 llamas, at the end of the year, we would have 1000 / 3 = 333.33 new llamas. We can’t have a decimal portion of a llama, though, so we’ll round the result to get 333 new llamas born. 1000 / 4 = 250 llamas will pass away, so we’ll end up with a total of 1000 + 333 - 250 = 1083 llamas at the end of the year.

Write a function called `population(start_size, end_size)`. The parameter `start_size` is the size the population starts at and `end_size` is the size the populations should end at. Your function should then calculate the (whole) number of years required for the population to reach at least the size of the end value.

Tip: don't forget to round the amount of llamas that are born and that die at each iteration.

Example usage:

    years = population(1200, 1300)
    print(years)
    years = population(600, 3000)
    print(years)

Expected output:

    1
    21

### Assignment 4: Improvement

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

Write a function `biggest_improvement(filename)`. That finds the date on which Barcelona made the biggest improvement with respect to the match before. This is only measured in goals for Barcelona. Goals for the opponent are ignored. For example on 17/09/11 Barcelona scored 8 goal against Osasuna this is an improvement of 6 goal with respect to the match before. But this is not the biggest improvement.

Example usage:

    biggest_improvement_date = biggest_improvement('barca.txt')
    print(biggest_improvement_date)

Expected output:

    16/03/14

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.

Example usage:

    biggest_improvement_date = biggest_improvement('barca_short.txt')
    print(biggest_improvement_date)

Expected output:

    17/09/11

Tips:

1. You can load files using: `input_file = open(filename, 'r')`
2. Don't forget to close the file: `input_file.close()`
# Exam Scientific Programming 1

Date: October 24 2022

This is a digital exam. The exam consists of 3 assignment in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam5

# Rules

- Create one file for all your solutions called `sp1_exam5.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Twoish


Write a function called `twoish(n)`. The functions approximates the number two by calculating the sequence $$1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \ldots$$ repeated $$n$$ times. So we compute the sum for $$\frac{1}{x}$$ where $x$ starts at 1 and is doubled at every iteration.

Example usage:

    almost_two = twoish(10)
    print(almost_two)
    less_two = twoish(2)
    print(less_two)

Expected output:

    1.998046875
    1.5

### Assignment 2: Hamming

Hamming distance is a metric used to compare texts. Normally you compare texts per letter, but we're going to compare them per word. You look at the individual words of both texts. You compare the first word of each texts. If they're the same, you count 1 point. If they're different you count 0. You do the same for the second word of each string, then the third, etc. The hamming distance is simply all points added up.

Write a function called `hamming_distance(text1, text2)` that compares two texts this way. Bear in mind some edge cases:

- If two texts have a different amount of words, you limit the comparison to the shortest of the two lengths.
- The function should not be case sensitive and not sensitive to punctuation.

Example usage:

    pretty_text = hamming_distance("Norwegian Wood", "Norwegian Fjord")
    print(pretty_text)
    pretty_text = hamming_distance("I love deadlines. I love the whooshing noise they make as they go by.",
                                   "I LOVE pizza. I love the round shape they have.")
    print(pretty_text)

 Expected output:

    1
    6

Tips:

- You can split a text into a list of words using the `text.split()` method.
- You can remove punctuation and space with the `text.strip(' .,!?;:')` method.

### Assignment 3: Populations

Say we have a population of n llamas. Each year, n / 3 new llamas are born, and n / 4 llamas pass away.

For example, if we were to start with n = 1200 llamas, then in the first year, 1200 / 3 = 400 new llamas would be born and 1200 / 4 = 300 llamas would pass away. At the end of that year, we would have 1200 + 400 - 300 = 1300 llamas.

To try another example, if we were to start with n = 1000 llamas, at the end of the year, we would have 1000 / 3 = 333.33 new llamas. We can’t have a decimal portion of a llama, though, so we’ll round the result to get 333 new llamas born. 1000 / 4 = 250 llamas will pass away, so we’ll end up with a total of 1000 + 333 - 250 = 1083 llamas at the end of the year.

Write a function called `population(start_size, end_size)`. The parameter `start_size` is the size the population starts at and `end_size` is the size the populations should end at. Your function should then calculate the (whole) number of years required for the population to reach at least the size of the end value.

Tip: don't forget to round the amount of llamas that are born and that die at each iteration.

Example usage:

    years = population(1200, 1300)
    print(years)
    years = population(600, 3000)
    print(years)

Expected output:

    1
    21

### Assignment 4: Improvement

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

Write a function `biggest_improvement(filename)`. That finds the date on which Barcelona made the biggest improvement with respect to the match before. This is only measured in goals for Barcelona. Goals for the opponent are ignored. For example on 17/09/11 Barcelona scored 8 goal against Osasuna this is an improvement of 6 goal with respect to the match before. But this is not the biggest improvement.

Example usage:

    biggest_improvement_date = biggest_improvement('barca.txt')
    print(biggest_improvement_date)

Expected output:

    16/03/14

You can use the file [barca_short.txt](barca_short.txt) to test and debug your own code. This file contains only 4 matches.

Example usage:

    biggest_improvement_date = biggest_improvement('barca_short.txt')
    print(biggest_improvement_date)

Expected output:

    17/09/11

Tips:

1. You can load files using: `input_file = open(filename, 'r')`
2. Don't forget to close the file: `input_file.close()`
