---
title:  "Let's Play with Words - Building a Python Hangman Game"
date:   2023-09-27
---

Welcome back to PyMakers, your go-to destination for Python projects that combine wordplay and logic. In this project, we're diving into the world of word games by building a "Hangman Game" using Python. Hangman is a classic word-guessing game that challenges your vocabulary and deduction skills.

<h4>Why a Hangman Game?</h4>

Word games are not only fun but also educational. By creating a Hangman Game in Python, you'll not only learn about word selection and user interactions but also have a game that's both entertaining and intellectually stimulating. It's a project that brings words to life in an engaging way.

<h4>The Python Code</h4>

Let's jump straight into the Python code for our Hangman Game:

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

print("Welcome to the Hangman Game!")

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
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We create a list of words, <code>words</code>, from which the game will randomly select a word to guess.</li>
	<li>We initialize a variable, <code>word_to_guess</code>, with a randomly chosen word from the list.</li>
	<li>We create a list, <code>guessed_word</code>, to keep track of the guessed letters in the word.</li>
	<li>We set the number of maximum attempts, <code>max_attempts</code>, and initialize an <code>attempts</code> counter.</li>
	<li>Inside the game loop, we display the current state of the word with underscores for unguessed letters.</li>
	<li>We ask the player to guess a letter, and if it's in the word, we reveal its position in <code>guessed_word</code>.</li>
	<li>The game continues until the player guesses the word or runs out of attempts.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Python Hangman Game. This project combines wordplay, logic, and deduction to provide an engaging word-guessing experience.

Whether you're challenging your vocabulary or enjoying a game with friends, the Hangman Game is a fantastic way to explore the world of words and have fun while doing it. Stay tuned for more Python projects that blend creativity with wordplay. Happy coding! 🐍✨


