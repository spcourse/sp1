# Reformatting text

Create a file called `reformatting.py` and implement a function `text_to_lines(text, max_length)` which neatly formats the given text into lines of length `max_length`. Words should not be cut off, but moved to the next line when necessary.

    >>> source_text = "ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsense. It is also a common learning tool for keyboard classes, since all four keys are located on Home row." # from the wikipedia
    >>> print(source_text)
    ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY o
    r QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsen
    se. It is also a common learning tool for keyboard classes, since all four keys are located on H
    ome row.
    >>> print(text_to_lines(source_text, 94))
    ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY
    or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless
    nonsense. It is also a common learning tool for keyboard classes, since all four keys are
    located on Home row.


## Background

If you know how to split, as well as how to join strings again, you might implement a function that *reformats* text. In this case, we will create a formatter that ensures a text has a maximum number of characters per line. As you can see, when printing such a long string by itself, it doesn't really look *nice*: the newlines have been inserted in the middle of words. We can do better!

In strings, newlines can be inserted by writing `\n`. So you might do this[^1]:

    >>> text = "Beautiful python\nExplicit and simple form\nWinding through the clouds"
    >>> print(text)
    Beautiful python
    Explicit and simple form
    Winding through the clouds

You may also add a newline to an existing string:

    text = "Thought"
    text += "\n"
    text += "Leader"


## Strategy

1. Split up the text into individual **words**.

2. Create a variable to hold the newly made string.

3. Consider each word to see if a newline has to be inserted **before** it.

   - (So how do you do this? Try "running" the algorithm on paper using very short examples.)

4. Add the newline if needed, and then the word.

5. When finished with all words, re-join the string and return it.

Notice that this looks quite a bit like the transform strategy!


## testing

    checkpy reformatting


[^1]: <https://www.heroku.com/art/python>
