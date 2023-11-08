---
title: "Your First Flask Application: Building a Web Page"
date: 2023-11-04
---

In the world of web development, Flask stands out as one of the most approachable and versatile tools for building web applications using Python. If you're eager to take your first step into web development, Flask is the ideal starting point. This blog will guide you through creating your very first Flask application, where you'll build a simple web page and gain essential insights into the core concepts of this micro-framework.

## Why Flask?

Before we dive into Flask, you might wonder why it's a popular choice for web development. Flask offers several advantages that make it a top pick for both beginners and experienced developers:

1. **Simplicity:** Flask's design emphasizes simplicity, making it an excellent choice for those new to web development. Its minimalistic approach allows you to focus on your application's functionality without being overwhelmed by unnecessary complexity.

2. **Flexibility:** Flask provides the freedom to organize your code and structure your project as you see fit. It doesn't impose a strict project structure, making it suitable for projects of various sizes.

3. **Active Community:** Flask boasts a thriving community of developers, which means you'll find extensive documentation, tutorials, and an array of third-party extensions to enhance your development experience.

4. **Extensibility:** While Flask is minimalistic, it's also highly extensible. As your project grows, you can integrate additional features and functionality to meet your evolving needs.

With these advantages in mind, let's get started with Flask and build your first web page.

## Prerequisites

Before we begin, ensure you have Python installed on your system. You can check if Python is installed by opening your terminal or command prompt and running:

```python
python --version
```

If Python is installed, you should see a version number. If not, you can download and install Python from the [official Python website](https://www.python.org/downloads/).

To manage Python packages and dependencies, we recommend using `pip`, which is the standard package manager for Python. You can check if `pip` is installed by running:

```python
pip --version
```

If `pip` is not installed, you can follow the [official installation instructions](https://pip.pypa.io/en/stable/installation/) to set it up.

## Installing Flask

Once you have Python and `pip` installed, you're ready to install Flask. Open your terminal or command prompt and use the following command:

```python
pip install Flask
```

This command installs Flask and its dependencies, making it available for use in your projects.

## Your First Flask Application

Let's dive into creating a simple Flask application. In this example, we'll build a web page that displays a welcoming message.

1. **Project Structure:** Start by creating a new directory for your Flask project. You can name it whatever you like. Inside the project directory, create a new Python file (e.g., `app.py`) to hold your Flask application.

2. **Writing the Flask Application:**

   In `app.py`, open your text editor or integrated development environment (IDE) and add the following code:

   ```python
   from flask import Flask

   # Create a Flask application
   app = Flask(__name__)

   # Define a route and view function
   @app.route('/')
   def hello():
       return "Welcome to My First Flask Web Page!"

   # Run the Flask application
   if __name__ == '__main__':
       app.run()
   ```

   This code sets up a basic Flask application with a single route ('/') and a view function (`hello()`) that returns a welcoming message.

3. **Running the Application:**

   Now, open your terminal or command prompt and navigate to the project directory where `app.py` is located. To run your Flask application, use the following command:

   ```python
   python app.py
   ```

   You should see output similar to the following:

   ```plaintext
    * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
   ```

   This message indicates that your Flask application is up and running on your local machine.

4. **Accessing Your Web Page:**

   Open your web browser and visit `http://127.0.0.1:5000/` or `http://localhost:5000/`. You'll see the welcoming message displayed in your browser: "Welcome to My First Flask Web Page!"

Congratulations! You've successfully created and run your very first Flask application.

## Understanding the Flask Application

Let's break down the key components of the Flask application you've just created:

- `from flask import Flask`: This line imports the Flask class from the Flask library.

- `app = Flask(__name__)`: Here, we create a Flask web application named `app`. The `__name__` variable is a built-in Python variable that tells Flask where to find resources such as templates and static files.

- `@app.route('/')`: This line defines a route using a decorator. In Flask, a route is a URL pattern to which the application responds. In this case, the route is the root path ('/').

- `def hello()`: This is a Python function that defines what should happen when a user visits the root path.

- `return "Welcome to My First Flask Web Page!"`: Inside the `hello()` function, we return a welcoming message as the response.

- `if __name__ == '__main__':`: This conditional statement ensures that the app runs only if the script is executed directly, not when it's imported as a module in another script.

- `app.run()`: Finally, we run the Flask application using `app.run()`. This command starts a local development server that listens on `http://127.0.0.1:5000/`.

## Customizing Your Flask Web Page

With your first Flask web page up and running, it's time to explore how you can customize and expand it to meet your project's specific needs. Here are some ways to enhance your Flask application:

### Adding More Routes

In your Flask application, you can define additional routes by creating more view functions. Each route corresponds to a specific URL, and the associated view function determines the content to display.

For example, to create a new page that displays your resume, you can add the following code to `app.py`:

```python
@app.route('/resume')
def resume():
    return "This is my resume page."
```

Now, when you visit `http://127.0.0.1:5000/resume`, you'll see the message "This is my resume page."

### Using HTML Templates

While displaying messages directly in your view functions works for simple cases, Flask allows you to use HTML templates for rendering more complex web pages with dynamic content. Templates make it easier to separate the presentation from the application logic.

To use templates, create a directory called `templates` in your project directory and add an HTML file inside it. For instance, create a file named `index.html` with the following content:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Welcome Page</title>
</head>
<body>
    <h1>Welcome to My First Flask Web Page!</h1>
</body>
</html>
```

Next, you can modify your `app.py` to render this template:

```python
from flask import Flask, render_template

app = Flask(__name

__)

@app.route('/')
def hello():
    return render_template('index.html')

if __name__ == '__main__':
    app.run()
```

By using `render_template()`, Flask will render the `index.html` template and display it as your web page.

### Handling Form Submissions

Flask enables you to create and handle forms, allowing users to input data and interact with your application. You can implement forms for various purposes, such as user registration, login, and contact forms.

For example, you can create a simple contact form using Flask-WTF, an extension that integrates Flask with the popular WTForms library.

```python
from flask import Flask, render_template, request
from flask_wtf import FlaskForm
from wtforms import StringField, SubmitField

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your_secret_key'

class ContactForm(FlaskForm):
    name = StringField('Name')
    email = StringField('Email')
    submit = SubmitField('Submit')

@app.route('/contact', methods=['GET', 'POST'])
def contact():
    form = ContactForm()

    if form.validate_on_submit():
        name = form.name.data
        email = form.email.data
        # Process the form data here (e.g., send an email)
        return f'Thank you, {name}! Your message has been sent.'

    return render_template('contact.html', form=form)

if __name__ == '__main__':
    app.run()
```

This code defines a contact form and a route to handle form submissions.

### Database Integration

As your Flask project grows, you may need to store and retrieve data. Flask allows you to integrate databases to manage data efficiently. You can use databases like SQLite, PostgreSQL, or SQLAlchemy to handle data storage.

### User Authentication

To secure your web application, you can implement user authentication and authorization features. Libraries like Flask-Login and Flask-Principal can help you manage user sessions and permissions.

### Styling with CSS

Enhance the visual appearance of your web pages by using Cascading Style Sheets (CSS). You can create and link CSS files to your HTML templates to customize the design and layout of your application.

## Conclusion

Flask is an excellent choice for beginning your journey into web development with Python. Its simplicity and flexibility allow you to start with small, manageable projects and gradually expand your skills to tackle more complex tasks. By building your first web page in Flask, you've acquired valuable experience in creating routes, handling views, and serving content to users. As you continue exploring Flask and web development, you'll unlock endless possibilities to craft interactive, dynamic, and engaging web applications. Happy coding!