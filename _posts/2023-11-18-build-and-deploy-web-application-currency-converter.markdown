---
title: "Crafting Your Own Currency Converter Web App: A Step-by-Step Guide"
date: 2023-11-18
---

Greetings, fellow Python enthusiasts! Today, we embark on an exciting journey to create a Currency Converter web application using the power of Python and Flask. This guide will walk you through each step, from setting up the project structure to deploying your creation on the web. So, let's dive in and make some currency magic happen!

If you’re interested in testing out the completed project, click on this link: [PyMakers Currency Converter](https://pymakers-currency-converter.onrender.com/)

Visit my github to get the complete source code: [Currency Converter on GitHub](https://github.com/Jeff-Matriz/CurrencyConverterWebApp/tree/main)

Get you free currency API here(Not affiliated but highly recommended platform): [Free Currency API](https://freecurrencyapi.com/)

Signup to this awesome website [Render.com](https://render.com) to deploy your app for free.

## Project Structure

Before we start writing code, let's lay the foundation for our project. Here's the basic structure we'll be using:

```plaintext
CurrencyConverter/
|-- venv/
|-- templates/
|   |-- index.html
|   |-- result.html
|-- app.py
|-- requirements.txt
```

This structure includes a virtual environment (`venv`), two HTML templates for the web pages, the main Python script (`app.py`), and a requirements file (`requirements.txt`) specifying the necessary dependencies.

## Crafting the HTML Templates

Our web app will consist of two pages: the main converter page (`index.html`) and the result page (`result.html`). We'll start by creating the HTML templates.

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Currency Converter</title>
    <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='css/styles.css') }}">
</head>
<body>
    <h1>PyMakers Currency Converter</h1>
    
    <form action="/convert" method="post">
        <label for="amount">Amount:</label>
        <input type="text" name="amount" required>

        <label for="from_currency">From Currency:</label>
        <select name="from_currency">
            {% for currency in currencies %}
                <option value="{{ currency }}">{{ currency }}</option>
            {% endfor %}
        </select>

        <label for="to_currency">To Currency:</label>
        <select name="to_currency">
            {% for currency in currencies %}
                <option value="{{ currency }}">{{ currency }}</option>
            {% endfor %}
        </select>

        <button type="submit">Convert</button>
    </form>
</body>
</html>
```

```html
<!-- result.html -->
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Currency Converter Result</title>
    <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='css/styles.css') }}">
</head>
<body>
    <h1>Conversion Result</h1>

    <p>{{ amount }} {{ from_currency }} is equal to {{ result }} {{ to_currency }}</p>

    <a href="/">Back to Converter</a>
</body>
</html>
```

Feel free to style these pages according to your preference, or let your users get creative and style them on their own.

## Coding the Flask Application

Now, let's jump into the heart of our project: the Flask application (`app.py`). This script will handle requests, fetch currency data, and perform the actual conversions.

```python
# app.py
from flask import Flask, render_template, request
import requests

app = Flask(__name__)

# Replace 'YOUR_API_KEY' with your actual API key
CURRENCY_API_KEY = 'YOUR_FREE_API_KEY'
CURRENCY_API_URL = f'FREE_API_URL={CURRENCY_API_KEY}'

@app.route('/')
def index():
    # Fetch currency data from the API
    currencies = get_currencies()
    return render_template('index.html', currencies=currencies)

@app.route('/convert', methods=['POST'])
def convert():
    amount = float(request.form['amount'])
    from_currency = request.form['from_currency']
    to_currency = request.form['to_currency']

    # Fetch currency data from the API
    currencies = get_currencies()

    # Convert the amount
    result = convert_currency(amount, from_currency, to_currency, currencies)

    return render_template('result.html', result=result, from_currency=from_currency, to_currency=to_currency)

def get_currencies():
    # Fetch currency data from the API
    response = requests.get(CURRENCY_API_URL)
    data = response.json()

    # Extract the currency codes
    currencies = list(data['data'].keys())

    return currencies

def convert_currency(amount, from_currency, to_currency, currencies):
    # Fetch currency data from the API
    response = requests.get(CURRENCY_API_URL)
    data = response.json()

    # Extract exchange rates
    exchange_rates = data['data']

    # Convert the amount
    if from_currency == 'USD':
        rate = exchange_rates[to_currency]
        result = round((amount * rate), 5)
    elif to_currency == 'USD':
        rate = exchange_rates[from_currency]
        result = round((amount / rate), 5)
    else:
        rate_from = exchange_rates[from_currency]
        rate_to = exchange_rates[to_currency]
        result = round((amount * rate_to / rate_from), 5)

    return result

if __name__ == '__main__':
    app.run(debug=True)
```

In this script, we define two routes: `/` for the main converter page and `/convert` to handle the conversion form submissions. The `get_currencies` and `convert_currency` functions fetch currency data and perform the conversions, respectively.

## Setting Up Dependencies

We need to specify the project's dependencies in a `requirements.txt` file. Open the file and add the following:

```plaintext
Flask==2.2.5
requests==2.31.0
gunicorn==21.2.0
```

These dependencies include Flask for our web framework, requests for making HTTP requests, and gunicorn for serving our application.

## Uploading to GitHub

It's a good practice to version control your code. If you don't have a GitHub account, create one, and then initialize a new repository. Once done, upload your project files.

## Deploying on Render

Now, let's deploy our Currency Converter on the web using [Render](https://render.com/).

1. Sign up for a Render account if you don't have one.

2. Create a new web service on Render.

3. Set the GitHub repository as the source for your service.

4. Configure the settings, including adding environment variables like `FREE_API_URL` for your API key.

5. Deploy your service.

Voila! Your Currency Converter is now live on the web. Users can access it by the Render-provided URL.

## Conclusion

Congratulations! You've successfully created a Currency Converter web app using Python and Flask. This project not only hones your web development skills but also introduces you to the world of APIs and deployment. Feel free to explore more features, add additional currencies, or enhance the styling of your web pages. The journey of coding is limitless, and with each project, you're one step closer to becoming a Python maestro. Happy coding!