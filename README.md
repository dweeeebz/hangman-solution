# Hangman
Hangman is a classic game in which a player thinks of a word and the other player tries to guess that word within a certain amount of attempts.

This is an implementation of the Hangman game, where the computer thinks of a word and the user tries to guess it. 

Milestone 1: Set up the environment

Created a new repository in GitHub

Milestone 2: Complete the ask_letter method
```
def ask_letter(self):
        '''
        Asks the user for a letter and checks two things:
        1. If the letter has already been tried
        2. If the character is a single character
        If it passes both checks, it calls the check_letter method.
        '''
        # TODO 1: Ask the user for a letter iteratively until the user enters a valid letter
        # TODO 1: Assign the letter to a variable called `letter`
        # TODO 1: The letter has to comply with the following criteria: It has to be a single character. If it is not, print "Please, enter just one character"
        # TODO 2. It has to be a letter that has not been tried yet. Use the list_letters attribute to check this. If it has been tried, print "{letter} was already tried".
        # TODO 3: If the letter is valid, call the check_letter method
        try:
             #while self.num_lives != 0 :
                letter = input("Please enter a letter ").lower()
                self.letter = letter
                if len(letter) > 1:
                    print(f"Please, enter just one character. Letters guessed {list(set(self.list_letters))}") 
                    # break
                elif letter in self.list_letters:
                    print(f"{letter}  was already tried. Letters guessed {list(set(self.list_letters))}") 
                else:
                    #self.list_letters.append(letter)
                    if self.check_letter(letter) == True:
                        print(f"Nice! '{letter}' is in the word! {self.word_guessed}")
                    else:
                        print(f"Sorry, '{letter}' is not in the word. You have {self.num_lives} lives left.")            
        except:
            #print("Game Over")
            raise Exception
```

Milestone 3: Define the initializer
```
class Hangman:
    '''
    A Hangman Game that asks the user for a letter and checks if it is in the word.
    It starts with a default number of lives and a random word from the word_list.
    
    Parameters:
    ----------
    word_list: list
        List of words to be used in the game
    num_lives: int
        Number of lives the player has
    
    Attributes:
    ----------
    word: str
        The word to be guessed picked randomly from the word_list
    word_guessed: list
        A list of the letters of the word, with '_' for each letter not yet guessed
        For example, if the word is 'apple', the word_guessed list would be ['_', '_', '_', '_', '_']
        If the player guesses 'a', the list would be ['a', '_', '_', '_', '_']
    num_letters: int
        The number of UNIQUE letters in the word that have not been guessed yet
    num_lives: int
        The number of lives the player has
    list_letters: list
        A list of the letters that have already been tried

    Methods:
    -------
    check_letter(letter)
        Checks if the letter is in the word.
    ask_letter()
        Asks the user for a letter.
    '''

    def __init__(self, word_list, num_lives=5):
        # TODO 2: Initialize the attributes as indicated in the docstring
        # TODO 2: Print two message upon initialization:
        # 1. "The mystery word has {num_letters} characters"
        # 2. {word_guessed}
        # Save variables as attributes
        self.word_list = word_list # List of words to be used
        self.word = random.choice(word_list) # Mystery word to be guessed
        self.word_guessed= ['_' for i in self.word] # Mystery word printed as a list of unknown letters [ _, _, _,...]
        self.num_letters = len(self.word) # Number of letters of mysstery word
        self.num_lives = num_lives # Number of lives left after each round
        self.list_letters = []
        print(f"The mystery word has {self.num_letters} characters\n {self.word_guessed}")
```
Milestone 4: Complete the "ask_letter" method
(above)

Milestone5: Putting it all together 



```
