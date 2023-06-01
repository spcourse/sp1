# Exam Scientific Programming 1

Date: June 1 2023

This is a digital exam. The exam consists of 4 assignments in which you have to write a short python program.

You're only evaluated based on the _correctness_ of your solutions, code design is not important. So, you don't have to worry about comments or style guides.

You can test your code using checkpy. First download the tests for the exam:

    checkpy -d /spcourse/exam-tests

Run checkpy:

    checkpy sp1_exam8

# Rules

- Create one file for all your solutions called `sp1_exam8.py`. This is the file you'll hand in at the end of your exam.
- You're not allowed to use `numpy` or any other external Python module.
- You're only allowed to use the websites sp1.mprog.nl/sp2.mprog.nl. You're not allowed to use any other website.
- You cannot get any help with programming during the exam.
- Submit your solutions when you're done. **Check with the teacher present if you handed in your assignment correctly before leaving the exam venue.**

### Assignment 1: Common

Create a function called `common_elements(list1, list2)`. The function returns a list that contains only the elements that exist in both `list1` and `list2`. You may assume that neither `list1` nor `list2` contain duplicate elements.

Example usage:

    print(common_elements([1, 2, 3], [3, 4, 2, 8]))
    print(common_elements([18], ["a", "b", "c"]))

Expected output:

    [2, 3]
    []


### Assignment 2: Right
Implement the `right_justify(lines)` function in the provided code. This function right justifies each line of text in the input list `lines` by adding the appropriate amount of spaces to the left.

The `right_justify` function performs the following steps:

1. It determines the longest line in the input list `lines`. This is required to calculate the amount of padding for all the other lines.
2. For each line in `lines`, it calculates the number of spaces needed to right justify the line. This can be done by finding the difference between the length of the longest line and the length of the current line.
3. It adds the calculated number of spaces at the beginning of each line.
4. It collects all the right-justified lines in a new list and returns this list.

> Tip 1: To create a string with a specific number of spaces, simply utilize the * operator. For example, you can generate a string consisting of 10 spaces by using the following code: padding = " " * 10.
>
> Tip 2: By combining strings and assigning them to a new variable, you can easily create a concatenated string. For instance, if you have two strings called string1 and string2, you can merge them together and store the result in a new string variable using the following syntax: new_string = string1 + string2.

Example usage:

    text = [
        "Right justification is a formatting technique.",
        "It aligns text along the right margin.",
        "Each line starts at the same position.",
        "The rest of the line fills with spaces.",
        "It creates a clean and organized look."
    ]


    right = right_justify(text)
    for line in right:
        print(line)

Expected output:

    Right justification is a formatting technique.
            It aligns text along the right margin.
            Each line starts at the same position.
           The rest of the line fills with spaces.
            It creates a clean and organized look.

### Assignment 3: Highland cattle

In this assignment you will model the population growth of Highland cattle, considering fertility and death rates, as well as the introduction of new cows by forest management on an annual basis. The objective is to **simulate the population growth until a specified threshold** is reached.

To accomplish this, you will need to implement the function `simulate_cattle_population(initial_population, fertility_rate, death_rate, extra_new_cows_per_year, threshold)`. The function accepts the following parameters:

- `initial_population`: The initial population of Highland cattle.
- `threshold`: The cattle count at which we stop the simulation. Once the population of Highland cattle is equal or bigger to this value, the simulation is ended.
- `fertility_rate`: The fertility rate determines the number of cows added to the population each year. It is calculated by multiplying the number of cows at the start of the year by this rate.
- `death_rate`: The death rate determines the number of cows removed from the population each year. It is calculated by multiplying the number of cows at the start of the year by this rate.
- `extra_new_cows_per_year`: At the end of each year, the forest management service introduces additional cows to the population to maintain diversity. The number of extra cows introduced each year is specified by the `extra_new_cows_per_year` parameter.

The function uses a loop to iteratively update the population size on a yearly basis until it reaches the specified 'threshold.' It then returns the number of years that have passed.

Example usage:

    initial_population = 100
    fertility_rate = 0.6
    death_rate = 0.3
    extra_new_cows_per_year = 5
    threshold = 500
    years = simulate_cattle_population(initial_population, fertility_rate, death_rate, extra_new_cows_per_year, threshold)
    print(f"Population reached the threshold of {threshold} after {years} years.")


Expected output:

    Population reached the threshold of 500 after 6 years.

### Assignments 4: Home matches

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

Write a function `number_of_home_matches_per_year(filename)`. That goes over all the matches and computes the total number of times _that Barca played a home match_ _for each year_. The result should be a list containing the number of home matches for each year. The file `barca.txt` contains the results for 4 consecutive years, so the result should be a list containing 4 numbers (the total number of home games per year). The total number of home matches for the first year (2011) is 9, so the first element of the list should be 9.

Example usage:

    totals = number_of_home_matches_per_year('barca.txt')
    print(totals)

    totals = number_of_home_matches_per_year('barca_short.txt')
    print(totals)

Expected output:

    [9, 18, 19, 11]
    [2]
