---
title:  "Rise and Shine with Python - Building a Basic Alarm Clock"
date:   2023-09-15
---

Welcome to the world of Python programming, where we'll explore a practical solution to a daily need: waking up on time! In this project, we'll create a Basic Alarm Clock, a useful tool for setting and managing alarms. It's a fun and functional project that showcases the versatility of Python.

<h4>Why a Basic Alarm Clock?</h4>

We all need a reliable way to wake up on time, and Python can help with that. By building a Basic Alarm Clock, you'll learn about time management, user interfaces, and creating practical applications. It's a project that combines utility and creativity.

<h4>The Python Code</h4>

Let's jump right into the Python code for our Basic Alarm Clock:

{% highlight ruby %}

import time
import winsound

def set_alarm():
    alarm_time = input("Enter the time for the alarm (HH:MM AM/PM): ")
    while True:
        current_time = time.strftime("%I:%M %p")
        if current_time == alarm_time:
            print("Time to wake up!")
            winsound.Beep(1000, 1000) #(frequency, duration in milliseconds)
            break
        time.sleep(10)  # Check every 10 seconds

print("Welcome to the Basic Alarm Clock!")

while True:
    print("Options:")
    print("Enter '1' to set an alarm")
    print("Enter '2' to exit")

    choice = input("Enter your choice: ")

    if choice == '2':
        print("Goodbye!")
        break

    if choice == '1':
        set_alarm()
    else:
        print("Invalid choice. Please choose a valid option.")

{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We import the <code>time</code> and <code>winsound</code> libraries. <code>time</code> helps us manage time, and <code>winsound</code> is used to produce an alarm sound.</li>
	<li>We define a function, <code>set_alarm()</code>, where the user can input the alarm time in the format HH:MM AM/PM. The function continuously checks the current time and triggers the alarm when they match.</li>
	<li>Inside the main program loop, we provide a menu with options: setting an alarm and exiting the program.</li>
	<li>Depending on the user's choice, we either set an alarm using the <code>set_alarm()</code> function or exit the program.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've created a Basic Alarm Clock in Python. This project introduced you to time handling, user input, and audio feedback, providing a practical solution to a daily challenge.

Stay tuned for more Python projects that will help you explore the exciting world of programming. Coding is all about simplifying tasks, having fun, and creating practical applications. Happy coding! 🐍✨

