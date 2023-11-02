---
title:  "Shorten and Share with Ease - Building a Python URL Shortener"
date:   2023-09-30
---

Welcome back to PyMakers, your hub for Python projects that simplify and enhance your digital experiences. In this project, we're diving into the world of URLs and links by building a "URL Shortener" using Python. A URL Shortener is a handy tool for transforming long and complex web addresses into concise and shareable links.

<h4>Why a URL Shortener</h4>
Long URLs can be cumbersome and challenging to share, especially in printed materials or on social media. By creating a URL Shortener in Python, you'll not only learn about web requests and string manipulation but also have a practical solution for making your links more user-friendly. It's a project that combines convenience and efficiency.

<h4>The Python Code</h4>

Let's jump straight into the Python code for our URL Shortener:

{% highlight python %}
import requests

def shorten_url(url):
    response = requests.post("https://tinyurl.com/api-create.php", data={"url": url})
    if response.status_code == 200:
        return response.text
    else:
        return "Failed to shorten the URL."

print("Welcome to the URL Shortener!")

while True:
    original_url = input("Enter the URL you want to shorten: ")
    shortened_url = shorten_url(original_url)
    print("Shortened URL:", shortened_url)

    another = input("Shorten another URL? (yes/no): ").lower()
    if another != "yes":
        print("Thank you for using the URL Shortener!")
        break
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We import the <code>requests</code> module for making HTTP requests to the TinyURL API.</li>
	<li>We define a <code>shorten_url()</code> function that takes a long URL as input and sends a request to the TinyURL API to shorten it.</li>
	<li>Inside the program loop, the user enters the original URL they want to shorten.</li>
	<li>We call the <code>shorten_url()</code> function to obtain the shortened URL from the TinyURL API.</li>
	<li>The shortened URL is displayed to the user.</li>
	<li>The user has the option to shorten another URL or exit the program.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Python URL Shortener. This project simplifies the process of transforming long URLs into short, shareable links.

Whether you're sharing links in printed materials or making your online posts more concise, the URL Shortener is a valuable addition to your digital toolkit. Stay tuned for more Python projects that simplify and enhance your digital experiences. Happy coding! 🐍✨