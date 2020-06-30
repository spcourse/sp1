# Strings

> You can follow along with the examples below by starting Python and typing the examples at the Python prompt. It is also advisable to try a few variations of the commands that you find below, in order to better understand strings and string operations.

A string is a *sequence* of characters. You can access the characters one at a time with the bracket operator:

	>>> fruit = 'banana'
	>>> letter = fruit[1]

The second statement selects character number 1 from fruit and assigns it to letter. The expression in brackets is called an *index*. The index indicates which character in the sequence you want (hence the name).

But you might not get what you expect:

	>>> print(letter)
	a

For most people, the first letter of `'banana'` is b, not a. But for computer scientists, the index is an offset from the beginning of the string, and the offset of the first letter is zero.

	>>> letter = fruit[0]
	>>> print(letter)
	b

So **b** is the 0th letter ("zero-eth”) of `'banana'`, **a** is the 1th letter ("one-eth”), and **n** is the 2th ("two-eth”) letter.

You can use any expression, including variables and operators, as an index, but the value of the index has to be an integer. Otherwise you get:

	>>> letter = fruit[1.5]
	TypeError: string indices must be integers, not float

## Length

`len` is a built-in function that returns the number of characters in a string:

	>>> fruit = 'banana'
	>>> len(fruit)
	6

To get the last letter of a string, you might be tempted to try something like this:

	>>> length = len(fruit)
	>>> last = fruit[length]
	IndexError: string index out of range

The reason for the IndexError is that there is no letter in 'banana' with the index 6. Since we started counting at zero, the six letters are numbered 0 to 5. To get the last character, you have to subtract 1 from length:

	>>> last = fruit[length-1]
	>>> print(last)
	a

Alternatively, you can use negative indices, which count backward from the end of the string. The expression `fruit[-1]` yields the last letter, `fruit[-2]` yields the second to last, and so on.

## Looping with strings

A lot of computations involve processing a string one character at a time. Often they start at the beginning, select each character in turn, do something to it, and continue until the end. This pattern of processing is called a *traversal*. One way to write a traversal is with a `while`-loop:

	index = 0
	while index < len(fruit):
	    letter = fruit[index]
	    print(letter)
	    index = index + 1

This loop traverses the string and displays each letter on a line by itself. The loop condition is `index < len(fruit)`, so when `index` is equal to the length of the string, the condition is `false`, and the body of the loop is not executed any further. The last character accessed is the one with the index `len(fruit)-1`, which is indeed the last character in the string.

---

**Exercise** --- Write a variation of this loop that takes a string as an argument and displays the letters backward, one per line. Create a Python file to test your loop!

---

Another way to write a traversal is with a `for` loop:

	for char in fruit:
	    print(char)

Each time through the loop, the next character in the string is assigned to the variable `char`. The loop continues until no characters are left.

The following example shows how to use concatenation (string addition) and a for loop to generate an abecedarian series (that is, in alphabetical order). In Robert McCloskey's book *Make Way for Ducklings*, the names of the ducklings are Jack, Kack, Lack, Mack, Nack, Ouack, Pack, and Quack. This loop outputs these names in order:

	prefixes = 'JKLMNOPQ'
	suffix = 'ack'

	for letter in prefixes:
	    print(letter + suffix)

The output is:

	Jack
	Kack
	Lack
	Mack
	Nack
	Oack
	Pack
	Qack

Of course, that's not quite right because "Ouack” and "Quack” are misspelled.

---

**Exercise** --- Modify the program to fix this error.

---

To take only some characters of a string, we can employ a *conditional traversal* or *filter* strategy:

    codename = "Ardor2109"
    for char in codename:
        if char.isdigit():
            print(char)

Like above, the loop will consider all individual characters in the string. However, there is a conditional inside that loop, which will only trigger if the condition `char.isdecimal()` has been met. In this case, only characters that represent a numeric digit are printed:

    2
    1
    0
    9

The following program counts the number of times the letter `a` appears in a string:

    word = 'banana'
    count = 0
    for letter in word:
        if letter == 'a':
            count = count + 1
    print(count)

This program demonstrates another pattern of computation called a *counter*. The variable `count` is initialized to 0 and then incremented each time an `a` is found. When the loop exits, count contains the result: the total number of `a`'s.


## String methods

A *method* is similar to a function (it takes arguments and returns a value) but the syntax is different. For example, the method `upper` takes a string and returns a new string with all uppercase letters:

Instead of the function syntax `upper(word)`, it uses the method syntax `word.upper()`.

	>>> word = 'banana'
	>>> new_word = word.upper()
	>>> print(new_word)
	BANANA

This form of *dot notation* specifies the name of the method, `upper`, and the name of the string to apply the method to, `word`. The empty parentheses indicate that this method takes no argument.

A method call is called an *invocation*; in this case, we would say that we are invoking `upper` on the word.

---

**Exercise** --- There is a string method called count that is similar to the function `count` above. Read the documentation of this method and write an invocation that counts the number of `a`s in `'banana'`.

---

**Exercise** --- Read the documentation of the string methods at [https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str). You might want to experiment with some of them to make sure you understand how they work. `strip` and `replace` are particularly useful.

---

> The documentation uses a syntax that might be confusing. For example, in `find(sub[, start[, end]])`, the brackets indicate optional arguments. So `sub` is required, but `start` is optional, and if you include `start`, then `end` is optional.

## The `in` operator

The word `in` is a boolean operator that takes two strings and returns `True` if the first appears as a *substring* in the second:

	>>> 'a' in 'banana'
	True
	>>> 'seed' in 'banana'
	False

For example, the following function prints all the letters from `word1` that also appear in `word2`:

	def in_both(word1, word2):
	    for letter in word1:
	        if letter in word2:
	            print(letter)

With well-chosen variable names, Python sometimes reads like English. You could read this loop, "for (each) letter in (the first) word, if (the) letter (appears) in (the second) word, print (the) letter."

Here's what you get if you compare apples and oranges:

	>>> in_both('apples', 'oranges')
	a
	e
	s


## Transforming strings

You have seen the `upper()` method for strings, which changes each letter of a string into uppercase. Using a `for` loop, it is possible to write functions like `upper()`:

    transformed = ""
    for letter in word:
        if letter in "aeiouy":
            transformed += "."
        else:
            transformed += letter

This loop will change each vowel in the text into a period. Let's see what would happen if `word` is `"Hello, world!"`:

    H.ll., w.rld!

What we do here is use the loop to create a completely new string and (conditionally) add letters to it. We can decide during the loop what we would like to add to the string, if anything. This is called a *transform* strategy.

(From: Think Python)
