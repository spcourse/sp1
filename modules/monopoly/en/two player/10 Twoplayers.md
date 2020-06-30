## Assignment 3: Realistic addition: two players

In real life Monopoly is played by two players. Part of this assignment is first evaluating what the advantage is of the starting player and subsequently study how to repair the disadvantage player two has.
 
![](Balans.png){:.inline}{: style="width:35%"}

Note: We're going to edit the code from assignment 1 and 2. To make sure a working copy of that code is stored, we'll make a new file. Create a file called `monopoly_realistic.py` and copy the code we've written up til now into the new file and continue with this new file.

#### [part 3a] advantage of player 1

First add a second player to your simulation, let both players start with 1500 euros of starting money and determine the difference in number of properties between both players the moment all streets have been bought up. This difference will differ each game. That's why you should simulate 10000 games, so you can make an accurate estimation of the average difference. You'll see that player 1 does indeed have a small advantage over player 2.

The goal is to figure out the difference by simulating a large amount of games:
{: .language-python}
	Monopoly simulator: two players, 1500 euro starting money, 10000 games
    On average player 1 has X.XX more streets in their possession when all streets have been bought


**Strategy:**

  * Edit the *input* for function `simulate_monopoly()`
      - The function that simulates a game of Monopoly now requires the starting money for both players individually. Provide both as input arguments to the function:
      `simulate_monopoly(starting_money_p1, starting_money_p2)`

  * Edit the *output* of function `simulate_monopoly()`

    - Up until now we asked the function for the number of throws the game lasted for. Now however, we're only interested in the difference in the number of streets between both players: `delta = possession_count_p1 - possession_count_p2`. That is also the variable we want to provide as `return` value. **Note:** this value van be both positive and negative.

      delta = simulate_monopoly(starting_money_p1, starting_money_p2)
      print(f"After this game player 1 had {delta} more streets than player 2.")

  * Keep track of how much money both players have and what their individual positions are.

    * At the start of the game for example their positions are: `position_p1 = 0` and `position_p2 = 0`, but the brave among you can also keep track of their positions in a list like this: `positions = [0, 0]`. You have the same set of options for keeping track of the amount of money each player has. It is standard to use multiple variables, but it is more concise to use a list.

Always test your code for a single game and keep close watch whether your code behaves the way you expect it to. Only then should you increase the number of games. Again, use the same setup as you did in the function for the first assignment and now, aside from the number of games, also specify the starting money of both players: `simulate_monopoly_games(total_games, starting_money_p1, starting_money_p2)` en make sure you can answer the question.

Ultimately `print` the difference to the terminal:
{: .language-python}
  Monopoly simulator: two players, 1500 euro starting money, 10000 games
    On average player 1 has X.XX more streets in their possession when all streets have been bought

#### [part 3b] repairing the disadvantage of player 2

The question remains if and how we can fix this 'unfair' situation. One of the 'buttons' you can turn for this game is the amount of starting money the players receive. If player 2 has more starting money than they can overcome their disadvantage. Determine the amount of extra starting money player 2 should receive so they have, on average, as many streets as player 1 by the end of each game of Monopoly.

Declare a new function `equilibrium()` in which you repeatedly call the function `simulate_monopoly_games(total_games, starting_money_p1, starting_money_p2)` with different values for the starting money of player 2. Player 1's starting money is fixed at 1500 euros. Try this for an 'extra' amount of money for player 2 of 0, 50, 100, 150, 200 euros and each time print the average difference to the screen as follows:

    Starting money  [1500,1550]: player 1 on average X.XX more streets (player 2 50 euros extra)
    Starting money  [1500,1600]: player 1 on average X.XX more streets (player 2 100 euros extra)
    Starting money  [1500,1650]: player 1 on average X.XX more streets (player 2 150 euros extra)
    Starting money  [1500,1700]: player 1 on average X.XX more streets (player 2 200 euros extra)

If you've ran a couple simulation, you'll have a small data-set with which you can reproduce the graph from earlier and you should be able to make a decent estimation of the amount of extra money player 2 requires in order to restore the equilibrium.

There is of course a sum of money where the advantage switches towards player 2. Use that amount (and the amount before that) to make an estimation of the amount where the equilibrium is situated. Assume for this that the difference follows a linear course as function of the extra money player 2 receives. The answer has to be rounded to the nearest value of 25 euros.

{: .language-python}
	Monopoly simulator: 2 players
    If player 2 receives XXX euros more starting money, both players collect on average an equal number of streets


## Summary

The simulation that we've implemented here is a simplified version of the often-times very complex models with which large financial institutions assess risks and determine strategies. At the same time these simulations are used by political parties to predict the effects of different measures given a variation of scenarios.




