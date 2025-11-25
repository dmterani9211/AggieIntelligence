# AggieIntelligence
A Group Project for Team Aggie Intelligence for UC Davis AISC (AI Student Collective) Project 1 Aggie Hangman Beginner Project

import random
import string

word_bank = ["aggies", "ucdavis", "gunrock","silo","wellman","olson","egghead","california","giedt","tercero","segundo","latitude","cuarto","coho","asucd",
"courses", "passtime", "shields", "picnic","quad","pavillion","arboretum","mondavi","farmersmarket","downtown","creamery","pantry","squirrel","bike","cows",
"arc","undergraduate"]

hangcow_stages = [

r"""
            \   /
             \ /
              |
             / \
            /   \
""",

r"""
          / |_| \
""",

r""""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
""",

r"""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
          |_____|   \\
          |         ||
""",

r"""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
          |_____|   \\ 
          |         ||
          __/
""",

r"""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
          |_____|   \\ 
          |         ||
          __/__/
""",

r"""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
          |_____|   \\ 
          |         ||
          __/__/__/
""",

r"""
          / |_| \
        (/| • • |\)
           _____
          | 0 0 |___
          |_____|   \\ 
          |         ||
          __/__/__/__/
"""
]

max_attempts = len(hangcow_stages) - 1 #subtracting by 1 to get 6 attempts as needed
def choose_a_word():
    return random.choice(word_bank).upper()
def display_progress(word, guessed_letters):
    display = []
    #ch = character
    for ch in word:
        #seeing if a character is not an alphabetic letter
        if not ch. isalpha(): #shows spaces/punctuation
            display.append(ch)
        elif ch in guessed_letters:
            display.append(ch)
        else:
            #displays the word in dashes "-"
            display.append("_")
    #.join = displaying letter in word all together when guessed correctly
    return " ".join(display)

def game_loop():
    guessed_letters = set()
    word = choose_a_word()
    guessed = display_progress(word, guessed_letters)
    wrong_guesses = 0

    print("Welcome to UC DAVIS'S AGGIE INTELLIGENCE'S HANGCOW")
    print(f"You have {max_attempts} attempts to save the cow.")

    while True:
        print(hangcow_stages[wrong_guesses])
        print("Word: ", display_progress(word,guessed_letters))
        print("Guessed letters: ", " ".join(sorted(guessed_letters)) if guessed_letters else "None")
        print(f"Wrong guesses left: {max_attempts - wrong_guesses}")
        guess = input("Guess a letter or phrase:").strip().upper()

        if not guess:
            print("no input, please try again")
            continue

        #if player guesses more than one letter, assuming they are now trying to guess a word or finish the word
        if len(guess) > 1:
            if guess == word:
                print("\nCorrect! You were able to save the cow!")
                print("Word:", word)
                return True
            else:
                wrong_guesses += 1
                print("That full guess is incorrect, please try again")
        else:
            #the amount of letters on the screen is the same as the amount guessed
            letter = guess
            if letter not in string.ascii_uppercase:
                print("Please guess an English Letter (A-Z)")
                continue

            if letter in guessed:
                print("You already guessed this letter")
            else:
                guessed.add(letter)

            if letter not in word:
                wrong_guesses += 1
                print(f"No '{letter}'. The cow is getting worried...")
            else:
                print(f"Nice! '{letter}' is in the word")

        # Checking if the player won the game
        revealed = "".join([ch if (not ch.isalpha() or ch in guessed) else "_" for ch in word])
        #if there are no more blanks
        if "_" not in revealed:
            print("\nGuess the word, claim the win, classic Aggie move.")
            print("Word:", word)
            return True

        # Checking if the player has lost the game
        if wrong_guesses >= max_attempts:
            print(hangcow_stages[wrong_guesses])
            print("\n Oh no - the cow couldn't be saved.")
            print("The word was:", word)
            return False

        print("-" * 40)

def main():
    while True:
        game_loop()
        again = input("Do you want to play again? (y/n): ").strip().upper()
        if again != "Y":
            print("Thanks for playing Hangcow! Go Aggies!")
            break

if __name__ == "__main__":
            main()

'''
For the next part we want to see if our attempt was right 
or wrong so we need to reveal or not reveal part of the word, .maybe create the .txt file and words, 
also come to an agreement on perhaps a cow design for the hangman
steps:
1. input word (txt file or find a way for computer to generate word)
2. display number of spaces (*)
3. player guesses letter
    - reveal letter if attempt is correct and update spaces
    - if correct display partially guessed word and 
    - if incorrect, display body part
        - display incorrect letter or if player inputs wrong, they don't get penalized twice (print "retry")
4. repeat until player succeeds or loses
    - print something when player wins:
        o "Guess the word, claim the win-classic Aggie move."
    - print something when player loses:
        o 

    body parts can be last to code

the if statements
are true and false right
abd elif says if one condition is not true we will try another okay?
so what we need to do now is figure out how to code if an attempt is wrong , we not only need to print try again, 
but we also need to penalize the player by adding a body part and then having the player attempt to again Steps we need 
for this too is to check if the player has exceeded the amount of tries given

for each ---- for loop
until ----- while loop
 if statement ---- True or False 
 else ----- is if something is false or not true what is the alternative option 

'''


