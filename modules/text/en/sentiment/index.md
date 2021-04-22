# Sentiment analysis

In a file called `sentiment.py`, write a function `sentiment_of_text(text)` that calculates the *sentiment score* of the text.

    >>> sentiment_of_text("Pastel-colored 1980s day cruisers from Florida are ugly.")
    -1

## Background

If we have a lexicon of "good" and "bad" words, we may decide if the words in a text are indeed positive or negative in attitude. Researchers have, over the years, [collected](https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html#lexicon) many words in the English language that are associated with either positive or negative attitudes. These lexicons have found their way into many applications that perform *sentiment analysis*, for example on texts from literature or famous Twitter accounts.

In this assignment, we will not only decide if single words are either negative, positive or neutral, we will also calculate the total score of all words in a given text. To do this, we define the score as follows:

| sentiment | score |  
| --------- | ----: |  
| negative  |    -1 |  
| neutral   |     0 |  
| positive  |     1 |  

When analyzing a text, this means that each positive word adds 1 to the total score, each negative word deducts 1, and neutral words (that do not belong to either of the other categories) do not influence the score at all.


## Strategy

1. Download [pos_words.txt](pos_words.txt) and [neg_words.txt](neg_words.txt).

2. Use this code for loading the word lists:

       def load_words(filename):
           content = open(filename)
           lines = content.read().splitlines()
           content.close()
           return lines

       def load_positive_words():
           return load_words("pos_words.txt")

       def load_negative_words():
           return load_words("neg_words.txt")

       pos_words = load_positive_words()
       neg_words = load_negative_words()

   Now you have two lists containing the words.

3. Write a function `sentiment_of_word(word)` that calculates the score of a single word. It should check if the word belongs to either word list and return the appropriate score, or if it doesn't, return 0. Make sure you clean the word before you calculate its sentiment score.

4. Write a function `sentiment_of_text(text)` that calculates and totals the sentiment score of all words in the text.


## Testing

First convince yourself that everything works as it should by trying out some sentences. You can add the following code to test your functions:

    total_score = sentiment_of_text("...")
    if total_score > 0:
        print("The text is mostly nice!")
    elif total_score < 0:
        print("The text talks about mad or bad stuff :(")
    else:
        print("The text is not opinionated or just messy.")

Now you're ready to test with checkpy:

    checkpy sentiment
