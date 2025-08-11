# NumberGuessingGame
The objective of this project is to build a simple number guessing game that challenges the user to identify a randomly selected number within a specified range.

#Accept lower and upper bounds from the user.
#Generate a random number in the selected range.
#Calculate the maximum allowed guesses using the binary search formula.
#Run a loop to take user guesses:
#If the guess is too high, print: "Try Again! You guessed too high."
#If the guess is too low, print: "Try Again! You guessed too small."
#If the guess is correct, print: "Congratulations!" and exit the loop.
#If the user runs out of chances, display the correct number and a message: "Better Luck Next Time!"
#**Future improvements:
#Add difficulty that adjusts the amount of chances

import random

print("Let's play a number guessing game.\nYou have 7 chances to guess the number. Let's go!")

low = int(input("Give the lower range: "))
high = int(input("Give me the higher range: "))

print(f"\nYou have 7 chances to guess the number between {low} and {high}. Let's start!")

num = random.randint(low, high)
ch = 7 #total chances
gc = 0 #guess counter

while gc < ch:
    gc += 1
    guess = int(input('Enter your guess: '))

    if guess == num:
        print(f'You got it! The number is {num}. You guessed it in {gc}')
        break
    
    elif gc >= ch and guess != num:
        print(f'Sorry, you lost :(. The number is {num}. Better luck next time.')

    elif guess > num:
        print('Too high! Try a lower number.')

    elif guess < num:
        print('Too low! Go higher.')
