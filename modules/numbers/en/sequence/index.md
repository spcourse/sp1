# Sequence

Write a program that finds the *longest continuous sequence of non-primes* under 10.000 and displays a short summary of the results.

	# python sequence.py
	The longest sequence non-primes under 10.000 starts at ... and ends at ...
	The sequence is ... long.

Carefully read what is required. Under the number 100 the answer should be as follows:

	The longest sequence non-primes under 100 starts at 90 and ends at 96
	The sequence is 7 long.

The assignment is about finding the longest sequence under the number 10.000.

## Background

Always develop a strategy using pen and paper. Don't immediately start coding. The 5--10 minutes you spend on writing out your thoughts are easily earned back when you convert your ideas into code.

To correctly understand the idea of a sequence of non-primes, write for example the first ten prime numbers on paper and measure the distance to one another: between 2 and 3 the difference is only one, whilst the difference between 13 and 17 is four (which means that there are 3 consecutive numbers between that are non-prime, 14, 15 and 16 to be precise).

## Specification

* Create a file called `sequence.py` and make sure it provides the same result when executed as shown in the example. Use your existing prime-finding program as a base. Make adjustments such that the program first generates a list of prime numbers that are smaller than the number 10.000. Since it is now certain how many numbers should be checked you can use a `for`-loop instead of a `while`-loop.

* Step (loop) subsequently through the list of prime numbers and each time determine how long the sequence of non-primes is between the current and last found prime number. Keep track of the longest sequence in a separate variable.

* Make sure your output is neatly formatted and is actually understandable and useful: first print the two non-prime numbers at the start and end of the sequence. Then on the next line, print the length of the sequence! Verify with the example at the top of this page.

## Testing

Once again carefully read the specification at the top of the assignment and make sure your program works exactly as specified. Test it by hand with 100 and 10.000.

Now you're ready to test:

	checkpy sequence
