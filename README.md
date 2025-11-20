# AggieIntelligence
A Group Project for Team Aggie Intelligence for UC Davis AISC (AI Student Collective) Project 1 Aggie Hangman Beginner Project
word_that_needs_to_be_guessed = input("Please enter a word to guess please do not put anything that contains * ")
word_that_needs_to_be_guessed.strip(word_that_needs_to_be_guessed)
###for this game short words will be excluded (using .txt file)
while '\t' in word_that_needs_to_be_guessed or '*' in word_that_needs_to_be_guessed:
    word_that_needs_to_be_guessed = input("Please enter a word to guess please do not put anything that contains * ")
    return word_that_needs_to_be_guessed


def letter_we_are_guessing(word_that_needs_to_be_guessed: str)
    letter_we_are_guessing = input("Please enter a letter")
    letter_we_are_guessing.lower()
    letter_we_are_guessing.strip(letter_we_are_guessing)
    return letter_we_are_guessing


def reveal_letter_we_are_guessing_is_right((word_that_needs_to_be_guessed: str

)

def partially_guessed_word

    if letter_we_are_guessing == word_that_needs_to_be_guessed:
        print("You are right")
        print(partially_guessed_word * len(word_that_needs_to_be_guessed))
        else print("incorrect, please try again")
        print(body_part)
# if statements are essentially True or False or Yes and No
# The function as a way to determine if something is present or not and is called Boolean
#

## Things we need in order for next steps , amount of attempts till becoming unalived
# no more txt file other player will 'enter' code word for other player to guess to make it a bit easier
# we will use len function to help the code know how many letters are comprised in the word we are trying to guess




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

