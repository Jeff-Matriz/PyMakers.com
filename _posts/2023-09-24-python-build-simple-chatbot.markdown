---
title:  "Let's Chat! Building a Python Simple Chatbot"
date:   2023-09-24
---

Welcome back to PyMakers, your creative playground for Python projects. In this project, we're diving into the world of conversational AI by building a "Simple Chatbot" using Python. Chatbots have become an integral part of our online experiences, and this project will give you a glimpse into the exciting field of natural language processing.

<h4>Why a Simple Chatbot?</h4>

Chatbots have a wide range of applications, from customer support to virtual assistants. By creating a Simple Chatbot in Python, you'll not only learn about conditional statements and user interactions but also have the foundation for developing more complex chatbots. It's a project that combines language and logic to create engaging conversations.

<h4>The Python Code</h4>

Let's dive straight into the Python code for our Simple Chatbot:

{% highlight ruby %}
import random

responses = {
    "hello": "Hello! How can I assist you today?",
    "how are you": "I'm just a computer program, but thanks for asking!",
    "bye": "Goodbye! Have a great day.",
    "default": "I'm sorry, I don't understand. Can you rephrase that?"
}

print("Welcome to the Simple Chatbot!")

while True:
    user_input = input("You: ").lower()
    response = responses.get(user_input, responses["default"])
    print("Chatbot:", response)

    if user_input == "bye":
        print("Chatbot: Goodbye!")
        break
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We define a dictionary, <code>responses</code>, that contains pre-defined responses for specific user inputs. These responses provide the chatbot's conversational capabilities.</li>
	<li>Inside the program loop, the user enters text, which is converted to lowercase for uniformity.</li>
	<li>We use the <code>responses.get()</code> method to retrieve a response based on the user's input. If the input is not recognized, a default response is used.</li>
	<li>The chatbot replies with the selected response.</li>
	<li>If the user inputs "bye," the chatbot responds and the conversation ends.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Simple Chatbot in Python. This project introduces you to the world of natural language processing and lays the foundation for developing more complex chatbots.

Whether you're exploring conversational AI or simply having a chat with your creation, this Simple Chatbot is a fun way to delve into the world of language and logic. Stay tuned for more Python projects that bring creativity and interactivity to your coding journey. Happy coding! 🐍✨