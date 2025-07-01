# CodeAlpha_PythonProgramming
This project is a Python-based console application that includes two mini programs:  1. Hangman Game 🎮   2. Rule-Based Chatbot 🤖    Both programs demonstrate the use of core programming concepts such as conditionals, loops, functions, string manipulation, and user input/output in Python. They are designed to be interactive and beginner friendly.
Absolutely! Here's a complete project description that combines both your tasks: the Hangman Game and the Basic Chatbot, ideal for submitting as a school/college-level Python project.

1️⃣ Task 1: Hangman Game 🎮

import random

# Predefined list of words

word_list=["demon","apple","india","anime","table","ocean"]

# Choose a random word from the list

word_to_guess=random.choice(word_list)
guessed_letters=[]
incorrect_guesses=0
max_incorrect_guesses=6

# Create a hidden version of the word

display_word=['_']*len(word_to_guess)

print("\U0001F3AE Welcome to Hangman!")
print("Guess the word,one letter at a time.")
print("You have 6 incorrect guesses. Good luck!")

# Game loop

while incorrect_guesses<max_incorrect_guesses and '_' in display_word:
    print('\nWord:',''.join(display_word))
    print('Guessed letters:',''.join(guessed_letters))
    guess=input("Enter a letter:").lower()
   
    if not guess.isalpha() or len(guess)!=1:
        print('Please enter a single alphabetic character.')
        continue
    if guess in guessed_letters:
        print("You've already guessed that letter.")
        continue
    guessed_letters.append(guess)

    if guess in word_to_guess:
        print("\U00002705 CORRECT!")

# Update the display word with the guessed letter
    
    for i in range(len(word_to_guess)):
        if word_to_guess[i]==guess:
            display_word[i]=guess
    else:
        incorrect_guesses+=1
        print(f'\U0000274C INCORRECT! You have {max_incorrect_guesses-incorrect_guesses}guesses left.')

# Game result
if '_' not in display_word:
   print('\n \U0001F389 CONGRATULATIONS! You guessed the word:',word_to_guess)
else:
    print('\n \U0001F480 GAME OVER! The correct word was:',word_to_guess)


2️⃣ Task 2: Basic Rule-Based Chatbot 🤖

def chatbot():
    
    print("\U0001F916 Chatbot:Hello!I'm your friend chatbot.Type 'bye' to exit.")

    while True:
        user_input=input('You:').lower()

        if 'hello' in user_input or'hi' in user_input:
            print("\U0001F916 Chatbot: Hi there \U0001F44B!")
        elif 'how are you' in user_input:
            print("\U0001F916 Chatbot:I'm doing great!Thanks for asking \U0001F60A")
        elif 'your name' in user_input:
            print("\U0001F916 Chatbot:I'm Scooby or you can also call me Chatbot 1.0.What's yours?")
        elif 'help' in user_input:
            print("\U0001F916 Chatbot:Sure! You can say 'hello',ask 'how are you',or say 'bye'.")
        elif 'bye' in user_input:
            print("\U0001F916 Chatbot:Goodbye! Have a nice day \U0001F600.")
            break
        else:
            print("\U0001F916 Chatbot: I'm not sure how to respond to that \U0001F914")

# Run the chatbot

chatbot()
