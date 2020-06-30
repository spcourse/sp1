# Word use

Implement a program that prints a sorted list of all the words in a given text string. Each word in the output should be unique, written in lowercase, and no remnants of punctuation marks or white space should be left in the words as printed.

    # python list_words.py
    original: The apple doesn't fall far from the tree.
    apple
    doesn't
    fall
    far
    from
    the
    tree


## Background

An important step in analyzing texts is *cleanup*. Earlier, you have split up a text into words. If you have had a peek at the results of splitting, you might have noticed that simply splitting doesn't actually give just the *words*:

    >>> "Gimme a line.".split()
    ['Gimme', 'a', 'line.']

We notice two things: `"Gimme"` is spelled using a capital G, and `"line."` is spelled using the period. Both things may prove a problem when analyzing the content of texts. That's why it's often necessary to strictly define the way words will be spelled and what kind of information will be allowed.

Given the description and example above, you will need to make sure that each word is converted to lowercase before analysis, and that any punctuation marks are removed from at least the right side of each word (are there any punctuation marks that are appended to the left of a word?).

> Note that in this assignment, we ignore the fact that some words may be names. In English, names are commonly spelled with a capital letter. As we do not have the means to check if words are names or otherwise, we simply assume the function need only work on texts composed of dictionary words. This is a big assumption and should be documented in the code!


## Strategy

1. Split up all "words".

2. Write a function called `cleanup(word)` that cleans a word using the guidelines above. Use methods from Pythons `string` library to do this.

3. Write a function called `text_to_unique_words(text)` that takes a text as input and outputs a list of unique words.

    * Pass all words through the `cleanup` function.
    * To make sure that the words are unique, you will need a variant of the transform strategy:

          unique_words = [...]
            for each word in words:
              only append to unique_words if it is not in there yet
          return all unique_words

    * Return a sorted list of unique words. If you want to sort a list you can use the function `sorted()` in python:

          sorted_list = sorted(unsorted_list)

4. print result as specified.

Tip: split up your code into functions (with meaningful names) as much as possible!


## Testing

First try to think of some testcases yourself. Some interesting examples could be:

- empty input
- 1-word input
- multiple-word input
- words with punctuation
- words with double blanks / empty words  "word<space><space>huh"

Now with checkpy:

    checkpy list_words
