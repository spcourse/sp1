# Greedy

Implement a program that calculates the minimum number of coins for a given sum of change.

	How much change is owed? 0.41
	4

## Background

![](coinchange.png)

In the distant past, when people actively paid for products using cash money, a coin holder, as can be seen above, was an invaluable asset to the inveterate bargain-hunter. The bothersome part was that for each coin a lever had to be pulled, a time consuming effort. Luckily we, computer scientists, are at the ready to minimize the number of coins that need to be handed over through use of "greedy algorithms".

A greedy algorithm is an algorithm that always makes the best local choice en route to the solution. It's like when you're cycling and at each intersection you choose the road that you think at that moment will lead you to your destination the quickest. These kinds of algorithms can lead, for some problems, to the optimal solution, but not by far for all of them.

Imagine a cashier that owes a customer some change, and this cashier has to press a lever for each coin they have to return, quarters (25c), dimes (10c), nickels (5c) and cents (1c). We're looking to solve this problem by pressing the lever one or multiple times, but wish to press that lever as few times as possible.

We can now imagine a "greedy" cashier. Who, every time they have to press a lever, presses the lever with the highest possible value that they're allowed to press. For example, if a customer is owed 41 cents, the cashier then presses the lever for the quarter first. The remainder of change is then (41 - 25 =) 16 cents. Now the cashier can no longer press the lever for 25 cents, since they would then return more money than what is owed. So they press the lever for the next highest value, a dime. Leaving only 6 cents of change to be handed out. This is followed by a press for a nickel and finally a cent. In total the customer receives one quarter, one dime, one nickel and one cent, resulting in 4 coins all together.

It turns out that such a greedy approach *always* results in the fewest coins to be handed out by the cashier. Which means the algorithm *guarantees an optimal solution* (note: this only applies for this set of coins). We do have to assume that the supply of coins never runs out.

How many coins are required exactly for any number of change owed? You tell us!

## Specification

* Create a file called `greedy.py` and implement a program that first prompts for the number of change owed and subsequently prints the minimum number of coins required.

* Assume that the user provides a whole number (integer), or a decimal number (float). The decimals in that case represent individual cents. So `3.21` means `3` dollar and `21` cents.

* [In case the user does not succeed in providing a correct input](https://en.wikipedia.org/wiki/Murphy's_law), make sure they can retry.

## Hints

* This program is structured somewhat like `water`: there is an explicit separation between *input*, *calculation* and *output*. The difference being that the calculation is no longer a single formula. You have to develop a complete *algorithm*!

* It is useful to use a single variable throughout your entire program in which you gradually develop the final solution: the number of coins that need to be handed out.

* Make sure that, if the user provided a float as input, you change that float into an integer. The coins we hand out are whole *cents* after all.

* To prevent any rounding errors or floating point imprecision when converting floats to integers, first round numbers by using `round()`. Try it out: `round(7.8)` and `round(7.2)`.

* The exact implementation for the problem is up to you. You could, for example, use loops, but you can also use the modulo operator `%`. Try and use it: `26 % 8`.

## Testing

	checkpy greedy

(You know how to test by now, right?)
