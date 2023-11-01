---
title:  "Creating Your First Python To-Do List"
date:   2023-09-05
permalink: /to-do-list-app/
---

Welcome to the world of Python programming, where fun and learning go hand in hand! Today, we're diving into a classic beginner project: building your very own To-Do List application. It's a fantastic way to practice Python and create something useful while you're at it.

<h4>Why a To-Do List?</h4>

To-Do lists are a great way to keep track of tasks and stay organized. Plus, creating a To-Do List in Python is an excellent exercise to get familiar with data structures, loops, and user input. So, let's get started!

<h4>The Python Code</h4>

We'll be using Python's built-in `list` to store our tasks. Here's the code:

{% highlight ruby %}
# Create an empty list to store tasks
tasks = []

# Main program loop
while True:
    # Menu options
    print("\nTo-Do List:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark as Done")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == '1':
        task = input("Enter a new task: ")
        tasks.append(task)
        print("Task added!")

    elif choice == '2':
        print("\nTasks:")
        for index, task in enumerate(tasks):
            print(f"{index + 1}. {task}")

    elif choice == '3':
        task_index = int(input("Enter the task number you completed: ")) - 1
        if 0 <= task_index < len(tasks):
            completed_task = tasks.pop(task_index)
            print(f"Completed: {completed_task}")
        else:
            print("Invalid task number!")

    elif choice == '4':
        print("Goodbye!")
        break

    else:
        print("Invalid choice. Please choose a valid option.")
{% endhighlight %}

<h4>How it Works</h4>
<ol>
    <li>We start by creating an empty list called tasks to store our to-do items.</li>
    <li>Inside the main loop, we display a menu with four options: Add Task, View Tasks, Mark as Done, and Exit.</li>
    <li>Depending on the user's choice, we perform the corresponding action. For instance, when the user selects "Add Task," we take their input and append it to the tasks list.</li>
    <li>When they choose "View Tasks," we display the tasks using a for loop, giving each task a number.</li>
    <li>If they opt to "Mark as Done," we ask for the task number and remove the completed task from the list.</li>
    <li>Lastly, choosing "Exit" ends the program.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created your very own Python To-Do List application. You've learned how to use lists, loops, and conditional statements, all while building a useful tool to keep track of your tasks. This is just the beginning of your Python journey, so keep exploring, experimenting, and most importantly, having fun with Python.

Stay tuned for more friendly Python projects, and remember, the world of coding is as exciting as you make it. Happy coding! 🐍✨