# hangman
Python version of popular guessing game.

## Intro

This is one of the first pieces of code I've written while learning Python. It comes from [100 Days of Code: The Complete Python Pro Bootcamp](https://www.udemy.com/course/100-days-of-code/?utm_source=adwords&utm_medium=udemyads&utm_campaign=Search_DSA_Alpha_Prof_la.EN_cc.ROW-English&campaigntype=Search&portfolio=ROW-English&language=EN&product=Course&test=&audience=DSA&topic=Python&priority=Alpha&utm_content=deal4584&utm_term=_._ag_162511578924_._ad_696197165262_._kw__._de_c_._dm__._pl__._ti_aud-2268488108799%3Adsa-1705455366924_._li_9061062_._pd__._&matchtype=&gad_source=1&gclid=Cj0KCQjwmt24BhDPARIsAJFYKk1n_RKZqRozrq50JSKKd9kj96AGmaDbbhZsI_oAjqboOmuLYrjKTlMaAjqoEALw_wcB&couponCode=2021PM20) that I've started some time ago. This is an awesome way of learning Python imo. Although I still haven't completed it I am already in love with it :innocent:

<br/>The below code is nothing fancy at all, but it was huge fun to be able to build it on my own - knowing few days earlier I had 0 Python knowledge.

<br/>Enjoy! There is more to come!

#100daysofcode


```python

import random

stages = ['''
  +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|   |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
  |   |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
      |
      |
      |
=========
''', '''
  +---+
  |   |
      |
      |
      |
      |
=========
''']

end_of_game = False
word_list = ["ardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)
word_length = len(chosen_word)
lives = 6

#Testing code
#print(f'Pssst, the solution is {chosen_word}.')

display = []
for _ in range(word_length):
    display += "_"

while not end_of_game:
    guess = input("Guess a letter: ").lower()

    for position in range(word_length):
        letter = chosen_word[position]
        if letter == guess:
            display[position] = letter
    if guess not in chosen_word:
        lives -= 1
        if lives == 0:
            end_of_game = True
            print("You lose.")
    print(f"{' '.join(display)}")

    if "_" not in display:
        end_of_game = True
        print("You win.")
    print(stages[lives])
```
