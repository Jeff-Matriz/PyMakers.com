---
title:  "Dive into Words - Building a Python Guess the Word Game"
date:   2023-09-18
---

Welcome back to PyMakers, where we continue our coding journey with yet another exciting project. This time, we're diving into the world of words and creativity by building a "Guess the Word Game." It's a project that combines language and logic, making it both fun and educational.

<h4>Why a Guess the Word Game?</h4>

Word games are a fantastic way to sharpen your vocabulary, boost your problem-solving skills, and challenge your friends. By creating a Guess the Word Game in Python, you'll not only learn about string manipulation but also discover how to create engaging and interactive word-based games.

<h4>The Python Code</h4>

Let's jump straight into the Python code for our Guess the Word Game:

{% highlight ruby %}

import random

# List of words to choose from
words = ["python", "coding", "fun", "project", "challenge", "game"]

# Select a random word from the list
word_to_guess = random.choice(words)

# Create a variable to keep track of the guessed word
guessed_word = ["_"] * len(word_to_guess)

# Number of attempts allowed
max_attempts = 6
attempts = 0

print("Welcome to the Guess the Word Game!")

while True:
    print(" ".join(guessed_word))
    letter = input("Guess a letter: ").lower()

    if letter in word_to_guess:
        for i in range(len(word_to_guess)):
            if word_to_guess[i] == letter:
                guessed_word[i] = letter
    else:
        attempts += 1
        print(f"Wrong guess! {max_attempts - attempts} attempts left.")

    if "".join(guessed_word) == word_to_guess:
        print(f"Congratulations! You guessed the word: {word_to_guess}")
        break

    if attempts == max_attempts:
        print(f"Out of attempts. The word was: {word_to_guess}")
        break


{% endhighlight%}

<h4>How it Works</h4>
<ol>
	<li>We start by importing the random module to choose a random word from a list.</li>
	<li>We create a list of words from which the game will choose a word to guess.</li>
	<li>We initialize a variable, word_to_guess, with a randomly chosen word from the list.</li>
	<li>We create a list, guessed_word, to keep track of the guessed letters in the word.</li>
	<li>We set the number of maximum attempts, max_attempts, and initialize an attempts counter.</li>
	<li>Inside the game loop, we display the current state of the word with underscores for unguessed letters.</li>
	<li>We ask the player to guess a letter and compare it to the selected word. If the letter is in the word, we reveal its position in guessed_word.</li>
	<li>The game continues until the player guesses the word or runs out of attempts.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Python Guess the Word Game. This project introduces you to random word selection, string manipulation, and conditional statements, while providing an engaging word-guessing game.

Stay tuned for more Python projects that will help you explore the exciting world of programming. Word games are just one way to use Python creatively. Happy coding! 🐍✨