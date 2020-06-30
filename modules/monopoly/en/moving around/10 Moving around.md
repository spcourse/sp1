# Monopoly: Donald Trump edition

Create a program that simulates a great number of games of a simplified version of the game Monopoly.

    Monopoly simulator: 1 player, Trump mode
    We simulated 10000 games
    It took an average of XXX throws for the player to collect all streets


## Background

We're going to simulate a large number of games of Monopoly in which we let 1 player go around the board and buy all the properties. We play the so-called Trump Mode. The player has infinite money and there is no competition. Goal of this assignment to determine the average number of throws after which all streets have been bought.

## Specification

* Create a new file called `monopoly.py`

* Declare a function `simulate_monopoly_games()` that can simulate a large number of games.

* The function `simulate_monopoly_games()` has one argument:

    - `total_games` is the number of games that get simulated
	
* The function `simulate_monopoly_games(total_games)` should `return` the number of throws required before all streets were held by the player.


## Dice

Each turn of the game starts with throwing two dice. That means two random numbers between 1 and 6. That can be achieved with the use of the `random()` function that we've learned to use earlier, but Python also comes with a special random-function meant for whole numbers: `randint(start, end)`.

{: .language-python}
    import random
    dice = random.randint(1, 6)

**Declare** a function `throw_two_dice()` without parameters that `returns` the result of throwing two dice. You'll want to use this function in your code like this:

      result = throw_two_dice()
      print(f"Total value of throwing two dice: {result}.")

**Declare** a function called `practice_with_dice()` to test your dice throws. Let it simulate a thousand throws and for each throw let it use two dice. `Print` for each throw the total value of the dice to the terminal and clearly display to the user when a 'double' has been thrown (the numbers on the two dices are identical). Keep track of the number of 'doubles' and `print` that number to the screen at the end of the function.

{: .language-python}
    throw 1: total value of 2 dice =  5
    throw 2: total value of 2 dice =  9
    throw 3: total value of 2 dice = 10
            Yes, we have a double: 5+5
    throw 4: ...
    throw 5: ...
    ..
    throw 1000: total value of 2 dice = 3

    print "The percentage of double throws = xx,xx percent"

Note: the function `practice_with_dice()` is not needed in the rest of the assignment. You can either remove it from your code or leave there, it's up to you.

## Moving around an empty board

We can now start our simulation by declaring a new function: `simulate_monopoly()`. We'll gradually expand this function until we can simulate a 'real' game of Monopoly. Let's start simple by having 1 player move one lap around the Monopoly game board en keep track of their exact position.

Repeatedly throw two dice and keep track on what property the player landed. `Print` that information to the screen. Each lap starts with position 0, prison is located at position 10 and the most expensive property is located at the second to last field; 39.

    After throw 1: position 6
    After throw 2: position 9
    After throw 3: position 17
    After throw 4: ...

Note: make sure the position is always denoted as an integer between 0 and 39, even when you've lapped the board multiple times. You could use the modulo (`%`) to achieve this, like earlier in module 1.

## Moving around the actual game board

Not every position on the board corresponds with a property (street, station or utility). The corners of the board are not for sale and also the "Chance" and "Community Chest" cards and taxes are not for sale (and also taxes are not deducted). Make a list of length 40, in which each position on the board is represented by its value. The first eleven positions would look like this:

{: .language-python}
    board_values = [0, 60, 0, 60, 0, 200, 100, 0, 100, 120, 0, ......]

Browse the internet for the further layout of the Monopoly board, so you can implement the full 40 fields and their values. If the value is lower than 1 euro (or more likely equal to zero) then the field is 'empty' (not for sale).

For each of the positions of the board you could `print` the following statement:

    After throw 1: position  6 (street)
    After throw 2: position  9 (street)
    After throw 3: position 17 (empty)
    After throw 4: ...

Implement this feature into your program.

## Moving around and buying properties

We'll now expand `simulate_monopoly()` with the possibility of buying properties and with that we'll have to keep track of which properties have/haven't been bought. We start by moving around the board in Donald Trump mode: we can buy anything, we're the only player in the game and we keep moving around until everything is in our possession. The question we have to answer in this assignment is as follows: "How long (how many throws) does it take for all streets to be ours?".

It is crucial that we monitor how many streets (and which ones) we have in our possession. This can be done through the use of a list (again 40 elements long) where each element represents whether the player owns the corresponding property. Start the list out as a collection of 40 zeros.

{: .language-python}
    possessions = [0, 0, 0, 0, ....., 0, 0]

Each time you land on a new position you can verify:

* the position is up for sale: street, station, utility?
* if so, is it still 'on the market'?

If, for example, you reach position 3 after the first trow and buy Whitechapel Road (or Brink, in the Dutch version) then you can update your list of possessions. 
Immediately afterwards the list would look like this:

{: .language-python}
    possessions = [0, 0, 1, 0, ....., 0, 0]

If a field is not for sale or the street is already in your possession then we throw the dice again and just move on. Make sure that each time you land on a field that can be bought, your program `print`s that fact to the screen and also how many properties you have in possession after buying that property.

    After throw 1: position  3 (street)
               player 1 has 1 property in their possession. There are still 27 fields for sale.

Since you know how many streets there are for sale in total, you also know when all available properties are in possession of the player. Stop throwing dice when that happens and instead `print` to the screen how many turns it took.

## Report the result

Now make sure that the function `simulate_monopoly()` `return`s the **number of throws** when it finishes simulating a game. You could also directly `print` it, but that is not the purpose of the function! Further on in the assignment we're going to be simulating a large number of Monopoly games and we don't want the program to `print` a message for each simulation. So use `return`.

Your code should operate as follows:

{: .language-python}

    number_of_throws = simulate_monopoly()
    print(f"Done! After throw {number_of_throws} the player owned all properties.")

## Multiple games and the average number of throws

We can now use the function `simulate_monopoly()` to simulate a single game of Monopoly. If you do this a couple of times you'll see that the number of throws required to collect all streets varies greatly from game to game. This is because near the end of a game you need a lot of luck to hit those few open fields left. The goal of this assignment is to find out how many throws the player *averagely* needs to bring all properties into their possession. To answer this question we'll need to simulate a huge number of games.

Declare a function `simulate_monopoly_games(total_games)` that will simulate a large number of games by repeatedly call the function `simulate_monopoly()`:

    for game in range(0, total_games):
        number_of_throws = simulate_monopoly()

1. Start with 1 game and increase that to 2, 10 and eventually 10000 when you're sure that the program functions properly.

2. For each game, keep track (in a list) of how many throws were necessary to collect all streets.

3. Create a graph (histogram) of that list after all games have finished simulating.

4. Determine the average number of throws necessary to collect all streets and `print` the result to the screen. Follow the format demonstrated at the start of the assignment:

    Monopoly simulator: 1 player, Trump mode
    We simulated 10000 games
    It took an average of XXX throws before the player to collect all streets

Tip: when you simulate a large number of games it is useful if the program reports what exactly is being executed at each moment in time. On the other hand, it is counter-productive if you have to scroll through line upon line of output. A way to resolve that issue is by, for instance, only `print` each 500 games of Monopoly the relevant information of that game. 

## And then: return the result

Finally make sure the function `simulate_monopoly_games(total_games)` `return`s the average number of throws that were required to collect all streets.

<!--## Testing

Update `checkpy` and test Monopoly:

    checkpy -u
    checkpy monopoly -->
