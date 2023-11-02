---
title:  "Unleash Your Creativity - Building a Python Basic Text Editor"
date:   2023-09-21
---

Welcome back to PyMakers, your creative playground for Python projects. In this project, we're diving into the realm of text manipulation by building a "Basic Text Editor." Whether you're a writer or just need a simple tool to jot down your thoughts, this project is designed to give you a taste of text processing in Python.

<h4>Why a Basic Text Editor?</h4>

Text editors are versatile tools used for writing, note-taking, and text manipulation. By creating a Basic Text Editor in Python, you'll not only learn about file handling but also have a practical, lightweight solution for your text-based needs. It's a project that combines simplicity and utility.

<h4>The Python Code</h4>

Let's jump right into the Python code for our Basic Text Editor:

{% highlight ruby %}
# Function to create or open a text file
def open_file(filename):
    try:
        file = open(filename, "r+")
    except FileNotFoundError:
        file = open(filename, "w+")
    return file

print("Welcome to the Basic Text Editor!")

while True:
    filename = input("Enter the name of the text file (e.g., my_file.txt): ")
    file = open_file(filename)

    print("Options:")
    print("1. Write a new text")
    print("2. Read the existing text")
    print("3. Exit")

    choice = input("Enter your choice (1/2/3): ")

    if choice == '1':
        text = input("Write your text: ")
        file.write(text)
        print("Text saved.")
    elif choice == '2':
        text = file.read()
        print("Text in the file:")
        print(text)
    elif choice == '3':
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please choose a valid option.")

    file.close()
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We define a function, <code>open_file()</code>, which takes a filename as input and tries to open the file in "r+" (read and write) mode. If the file doesn't exist, it is created in "w+" (write and read) mode.</li>
	<li>Inside the program loop, we ask the user to enter the name of the text file they want to create or open.</li>
	<li>We present the user with three options: writing a new text, reading the existing text, or exiting the program.</li>
	<li>Depending on the user's choice, we either write text to the file, read and display the text from the file, or exit the program.</li>
	<li>The file is closed when the user is done with it.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Basic Text Editor in Python. This project has introduced you to file handling, user input, and basic text manipulation while providing a simple but practical solution for writing and storing text.

Whether you're jotting down your thoughts or experimenting with text manipulation, this Basic Text Editor is a versatile tool at your disposal. Stay tuned for more Python projects that will help you explore the creative and functional aspects of programming. Happy coding! 🐍✨