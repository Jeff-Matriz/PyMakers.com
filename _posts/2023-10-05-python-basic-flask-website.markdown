---
title:  "Dive into Web Development - Building a Basic Website with Flask"
date:   2023-10-05
---

Welcome back to PyMakers, your gateway to the world of web development. In this project, we're diving into the world of web programming by building a "Basic Website with Flask" using Python. Flask is a lightweight web framework that allows you to create dynamic and interactive web applications.

<h4>Why a Basic Website with Flask?</h4>

Web development is an essential skill in today's digital age, and Flask is an excellent framework for those looking to get started. By creating a Basic Website with Flask in Python, you'll not only learn about web routing, templates, and dynamic content but also have the foundation for building more complex web applications. It's a project that combines creativity with technical skills.

<h4>The Python Code</h4>

Let's jump right into the Python code for our Basic Website with Flask:

{% highlight python %}
from flask import Flask, render_template #pip install Flask

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We import the <code>Flask</code> class from the Flask library.</li>
	<li>We create a Flask application instance and define a route for the home page ('/').</li>
	<li>When a user accesses the home page, the <code>home()</code> function is executed, and it renders an HTML template (index.html).</li>
	<li>The <code>if __name__ == '__main__':</code> block ensures that the Flask app runs when this script is executed directly, allowing us to test our website locally.</li>
	<li>You need to create an HTML template (index.html) that defines the structure and content of the home page.</li>
</ol>

Here's an example <code>html</code> you can use:

{% highlight html %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to My Flask Website</title>
</head>
<body>
    <header>
        <h1>Welcome to My Flask Website</h1>
    </header>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>
    <main>
        <section>
            <h2>About This Website</h2>
            <p>This is a simple Flask website that serves as an example for beginners in web development.</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2023 PyMakers.com</p>
    </footer>
</body>
</html>
{% endhighlight %}

You can save this code in an <code>index.html</code> file within a folder called "templates" in your Flask project directory. The <code>templates</code> folder is where Flask expects to find your HTML templates.

This example HTML template includes a basic structure with a header, navigation menu, main content area, and a footer. You can customize it further to suit your specific needs, adding more pages, styles, and content as required for your website.

<h4>Conclusion</h4>

Congratulations! You've just created a basic website with Flask, marking your entry into the world of web development. This project introduces you to web routing, HTML templates, and dynamic content delivery.

Whether you're building a personal website, a portfolio, or experimenting with web applications, Flask is a valuable tool for creating interactive web experiences. Stay tuned for more Python projects that help you explore the ever-evolving world of web development. Happy coding! 🐍🌐


