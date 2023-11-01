---
title:  "Building Your First Python Basic Calculator"
date:   2023-09-08
---

Welcome to the world of Python programming, where we transform complex tasks into fun and engaging projects. Today, we're diving into one of the classics: building a basic calculator. It's the perfect beginner project to not only practice Python but also create a practical tool that can perform simple arithmetic operations.

<h4>Why a Basic Calculator?</h4>

A calculator is a useful tool that everyone can appreciate. By building one in Python, you'll get to know how to take user input, perform mathematical operations, and present the results. It's a fantastic way to get started with Python, especially if you're new to coding.

<h4>The Python Code</h4>

We'll start by creating a calculator that can add, subtract, multiply, and divide. Here's the code:

{% highlight ruby %}
# Function to add two numbers
def add(x, y):
    return x + y

# Function to subtract two numbers
def subtract(x, y):
    return x - y

# Function to multiply two numbers
def multiply(x, y):
    return x * y

# Function to divide two numbers
def divide(x, y):
    if y == 0:
        return "Cannot divide by zero"
    return x / y

# Main program loop
while True:
    print("Options:")
    print("Enter 'add' for addition")
    print("Enter 'subtract' for subtraction")
    print("Enter 'multiply' for multiplication")
    print("Enter 'divide' for division")
    print("Enter 'exit' to end the program")

    user_input = input(": ")

    if user_input == "exit":
        print("Goodbye!")
        break
    elif user_input in ("add", "subtract", "multiply", "divide"):
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        
        if user_input == "add":
            print("Result: ", add(num1, num2))
        elif user_input == "subtract":
            print("Result: ", subtract(num1, num2))
        elif user_input == "multiply":
            print("Result: ", multiply(num1, num2))
        elif user_input == "divide":
            print("Result: ", divide(num1, num2))
    else:
        print("Invalid input")

{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We define four functions for addition, subtraction, multiplication, and division, each taking two numbers as input and returning the result.</li>
	<li>Inside the main program loop, we present a menu with options for the user to choose from: 'add', 'subtract', 'multiply', 'divide', and 'exit'.</li>
	<li>Based on the user's choice, we ask for two numbers and use the corresponding function to perform the operation. The result is displayed.</li>
	<li>If the user chooses 'exit', the program ends. If the input is not recognized, the program displays "Invalid input."</li>
</ol>

<h4>Conclusion</h4>

You've just created your very own Python Basic Calculator! This project introduced you to functions, user input, conditional statements, and basic arithmetic operations. It's a simple but essential step in your Python journey, so keep experimenting and exploring.

Stay tuned for more Python projects that will help you learn and have fun at the same time. In the world of coding, the possibilities are endless. Happy coding! 🐍✨