# Reformatting text

Create a file called `reformatting.py` and implement a function `text_to_lines(text, max_length)` which neatly formats the given text into lines of length `max_length`. Words should not be cut off, but moved to the next line when necessary.

    source_text = "ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsense. It is also a common learning tool for keyboard classes, since all four keys are located on Home row." # from the wikipedia
    print(source_text)
    print()
    print(text_to_lines(source_text, 94))

Expected ouput:

    ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY o
    r QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsen
    se. It is also a common learning tool for keyboard classes, since all four keys are located on H
    ome row.

    ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY
    or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless
    nonsense. It is also a common learning tool for keyboard classes, since all four keys are
    located on Home row.

## Specification

* The programm should contain the function `text_to_lines(text, max_length)`.
* The input of the function is a `string` called `text` and an `int` (number) called `max_length`.
* The output of the function is a string where each line contains at most `max_length` characters such that no words are cut off.

### Constraints

* You are only allowed to use the concepts that are discussed in this module. Except for the mentioned exceptions.
For an overview of those concepts have a look [here](/python/en/overview).
* You are *not* allowed to use the `import`-statement.
* You can use other string methods (like `split()`), mentioned in the python [string functions documentation](https://docs.python.org/3.7/library/stdtypes.html#string-methods).
* You can use the built-in python function `len()`.
* The function `text_to_lines(text, max_length)` should not contain any print statements.

## Background

If you know how to split, as well as how to join strings again, you might implement a function that *reformats* text. In this case, we will create a formatter that ensures a text has a maximum number of characters per line. As you can see, when printing such a long string by itself, it doesn't really look *nice*: the newlines have been inserted in the middle of words. We can do better!

In strings, newlines can be inserted by writing `\n`. So you might do this[^1]:

    text = "Beautiful python\nExplicit and simple form\nWinding through the clouds"
    print(text)

Output:

    Beautiful python
    Explicit and simple form
    Winding through the clouds

You may also add a newline to an existing string:

    text = "Yes, "
    text += "we"
    text += "\n"
    text += "can!"

Output:

    Yes, we
    can!

## Strategy

1. Split up the text into individual **words**.

2. Create a variable to hold the newly made string.

3. Consider each word to see if a newline has to be inserted **before** it.

   - (So how do you do this? Try "running" the algorithm on paper using very short examples.)

4. Add the newline if needed, and then the word.

5. When finished with all words, re-join the string and return it.

Notice that this looks quite a bit like the transform strategy!

## testing

### Testcases

Try some of the following testcases before you run checkpy:

#### Test 1

    test_text1 = "Row, row, row your boat. Gently down the stream. Row, row, row your boat. Gently down the stream."
    separate_lines = text_to_lines(test_text1, 25)
    
    for line in separate_lines.split("\n"):
        print(f"{len(line)}: {line}")

#### Expected output

    24: Row, row, row your boat.
    23: Gently down the stream.
    24: Row, row, row your boat.
    23: Gently down the stream.

#### Test 2

    test_text2a = "Computer science is no more about computers than astronomy is about telescopes."
    test_text2b = "If debugging is the process of removing software bugs, then programming must be the process of putting them in."
    print(text_to_lines(test_text2a, 35))
    print(text_to_lines(test_text2b, 40))

#### Expected output

    Computer science is no more about
    computers than astronomy is about
    telescopes.
    If debugging is the process of removing
    software bugs, then programming must be
    the process of putting them in.

#### Test 3

    test_text3 = "a bb ccc dddd"
    print(text_to_lines(test_text3, 4))
    print(text_to_lines(test_text3, 5))
    print(text_to_lines(test_text3, 7))
    print(text_to_lines(test_text3, 8))

#### Expected output

    a bb
    ccc
    dddd
    a bb
    ccc
    dddd
    a bb
    ccc
    dddd
    a bb ccc
    dddd

#### Test 4

    test_text4 = """He proposed in the dunes, they were wed by the sea, Their nine-day-long honeymoon was on the isle of Capri. For their supper they had one specatular dish- a simmering stew of mollusks and fish. And while he savored the broth, her bride's heart made a wish. That wish came true-she gave birth to a baby. But was this little one human Well, maybe."""
    print(text_to_lines(test_text4, 77))

#### Expected Output

    He proposed in the dunes, they were wed by the sea, Their nine-day-long
    honeymoon was on the isle of Capri. For their supper they had one specatular
    dish- a simmering stew of mollusks and fish. And while he savored the broth,
    her bride's heart made a wish. That wish came true-she gave birth to a baby.
    But was this little one human Well, maybe.

### Checkpy

    checkpy reformatting

Tip: Sometimes when the result seems correct but is not approved by checkpy there are some invisible mistakes (e.g. adding spaces at the end of a line). Try changing the space to a recognizable symbol to see if that might be the problem.

[^1]: <https://www.heroku.com/art/python>
