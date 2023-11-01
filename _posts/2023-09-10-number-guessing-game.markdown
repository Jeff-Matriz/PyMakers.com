---
title:  "A Fun Challenge – Building a Python Number Guessing Game"
date:   2023-09-10
---

Welcome to the world of Python programming, where learning is exciting and interactive! In this project, we'll dive into creating a classic Number Guessing Game. This is the perfect endeavor for those new to coding, offering both a learning experience and a bit of fun.

<h4>Why a Number Guessing Game?</h4>

Number guessing games are timeless and provide an excellent opportunity to explore fundamental programming concepts. By building one in Python, you'll gain insight into working with random numbers, user input, and conditional statements. Plus, it's a game everyone can enjoy!

<h4>The Python Code</h4>

Let's get started with the Python code for our Number Guessing Game:

{% highlight ruby %}
import random

# Generate a random number between 1 and 100
number_to_guess = random.randint(1, 100)

# Number of attempts
attempts = 0

print("Welcome to the Number Guessing Game!")

while True:
    user_guess = int(input("Guess the number (1-100): "))
    attempts += 1

    if user_guess < number_to_guess:
        print("Try a higher number.")
    elif user_guess > number_to_guess:
        print("Try a lower number.")
    else:
        print(f"Congratulations! You guessed the number {number_to_guess} in {attempts} attempts.")
        break

{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We start by importing the random module to generate a random number for the game.</li>
	<li>The program generates a random number between 1 and 100 and stores it in the variable number_to_guess.</li>
	<li>We set the initial number of attempts to 0 and display a welcome message.</li>
	<li>Inside the game loop, we ask the user to guess the number. The program increments the attempts counter with each guess.</li>
	<li>Based on the user's guess, we provide feedback. If the guess is too low or too high, the program provides hints.</li>
	<li>When the user correctly guesses the number, we display a congratulations message and the number of attempts taken.</li>
</ol>
<h4>Conclusion</h4>

Congratulations! You've created a Python Number Guessing Game. This project introduced you to random number generation, user input, conditional statements, and loops. It's an excellent starting point for learning and having fun with Python.

Stay tuned for more Python projects that will help you explore the exciting world of programming. Remember, coding is as enjoyable as you make it. Happy coding! 🐍✨