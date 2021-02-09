# Text statistics

You're going to write a program called `text_statistics.py` that will determine some properties of a given text fragment. One way to make sense of written texts is to calculate statistics about the form of the text. That is, we do not look at what the text *means*, but instead examine its superficial properties. Say we define the following variable:

	source_text = "ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsense. It is also a common learning tool for keyboard classes, since all four keys are located on Home row." # from the wikipedia

One statistic we could calculate is the length of the text, using the built-in `len()` function from Python.

	>>> print(len(source_text))
    296

But we can also define slightly more fine-grained statistics. In this assignment, you'll write four functions for text statistics that are not provided by Python. You will:

1. Count the number of letters in the text.
2. Count the number of words.
3. Count the number of sentences.
4. Compute the average word length.

# 1. Number of letters

## Specification

In `text_statistics.py`, write a function `number_of_letters_in(text)` that calculates how many letters are in a given string. Here's how one might use such a function:

### Examples

    print(number_of_letters_in("He counted more than 7 petals on each flower."))
	print(number_of_letters_in("ABCDE 9182 F"))

Expected output:

    35
    6

### Constraints

* You are only allowed to use the concepts that are discussed in this module. Except for the mentioned exceptions.
For an overview of those concepts have a look [here](/python/en/overview).
* You are *not* allowed to use the `import`-statement.
* You can't use the `str.count()` method.
* You can use other string methods (like `isalpha()`), mentioned in the python [string functions documentation](https://docs.python.org/3.7/library/stdtypes.html#string-methods)
* You can use the built-in python function `len()`

## Background

Let's define a *letter* to be any alphabetic character that occurs in a string. For our `source_text` above, this means that the number of letters is definitely less than the total length of the string, because it also contains spaces as well as periods. In other words, this new function is not the same as the `len()` function.

## Getting started

From the text above, copy the definition of the variable `source_text` into your file, for testing purposes. Then, define a function with the name `number_of_letters_in` and a single argument called `text`.

    def number_of_letters_in(text):
        # TODO

## Strategy

To do this, you'll need to build a loop that:

- examines each individual *character* of the string,
- then decide if that character is actually a *letter*,
- and if so, *count* it

When done examining, the final count should be `return`ed.

To test if something is a letter the string method `isalpha()` could be usefull.

### Testing

To test this function, you may add a few lines of tests below the function definition. Then run your file using:

    python text_statistics.py

Note: this also tests the functions you still need to implement below, so only pay attention to the first test for now.

# 2. Words

## Specification

Write a function `number_of_words_in(text)` which takes a string containing text, and returns how many words are in that text.

### Examples

    print(number_of_words_in("She stopped. Turned around. Oops, a bear. Just like that."))

Expected output:

    10

### Constraints

The same as above.

## Background

Texts are composed of words and sentences. To be able to analyze a text word-by-word or sentence-by-sentence, we might need to split things up. In this case, if we split up a text into words, we can calculate the number of words in the text.

## Strategy

Your strategy might look like this:

1. split up the original text using the `split()` method
2. calculate the length of the result from step 1
3. `return` the length from step 2

So in summary, you take the result of one method, use the result to call another, then return. Notice that here, we do not use a loop, because Python functions are available that do most of the work for us.


# 3. Sentences

## Specification

Write a function `number_of_sentences_in(text)` which takes a string containing text, and returns how many properly formatted sentences are in that text.

### Examples

    print(number_of_sentences_in("She stopped. Turned around. Oops, a bear. Just like that."))

Expected output:

    4

### Constraints

	The same as above.

## Background

We define a "properly formatted sentence" as any sentence closed with a full stop (or "period").

## Strategy

- You can use the same strategy as above, but use `split` in a different way. How should it be different?

- When you indeed use the same strategy as above, you might encounter a problem. Test your code with the sample text and check the results by hand!

      print(number_of_words_in(source_text))
      print(number_of_sentences_in(source_text))

  Most likely, you now see that the program counts 4 sentences, while you count only 3. There are 3 periods, so there are 3 well-formed sentences. How might we solve this problem?



# 4. Word length

## Specification

Write a function called `average_word_length(text)` that calculates the average length of the words in the text.

### Examples

    print(average_word_length("This is a brief note"))

Expected output:

    3.2

### Constraints

	The same as above.

## Background

If, like earlier, you split a text into words using `str.split()`, you will receive a `list` of strings, each string being one word from the text. You can perform analysis on each word by looping over this list.

## Strategy

- To start, create a variable that contains the result of splitting the text. You will use this variable as the source of further analysis.

- To calculate the length of each word, you can use the counter strategy. Modify the strategy to iterate over words in the split list, not over letters. Next, modify it to not *count* each word, but to *sum* the lengths of all words.

- When you have a variable containing the sum of the lengths of all words, you can calculate the average word length by dividing the sum by the number of words. You may retrieve the latter by calling the `number_of_words_in(text)` function that you wrote earlier.

## Testing all of it

    checkpy text_statistics
