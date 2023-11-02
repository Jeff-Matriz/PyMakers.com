---
title:  "Currency Conversion Made Easy - Building a Python Currency Converter"
date:   2023-09-19
---

Welcome back to PyMakers, your hub for Python projects that combine practicality and coding fun. In this project, we're delving into the world of finance and international travel by creating a "Currency Converter." This versatile tool will help you convert currencies effortlessly, whether you're planning a trip or managing your finances.

<h4>Why a Currency Converter?</h4>

Currency conversion is a common need, and Python can make it easy for you. By building a Currency Converter, you'll not only learn about user input and mathematical operations but also create a practical solution to a real-world challenge. It's a project that demonstrates the practical application of Python programming.

<h4>The Python Code</h4>

Let's dive right into the Python code for our Currency Converter:

{% highlight ruby %}
# Exchange rates as of the date you create the program
exchange_rates = {
    "USD": 1.0,
    "EUR": 0.85,
    "GBP": 0.75,
    "JPY": 110.0,
}

print("Welcome to the Currency Converter!")

while True:
    print("Available Currencies:")
    for currency in exchange_rates:
        print(currency, end=" ")
    print()

    from_currency = input("Enter the currency you have (e.g., USD): ").upper()
    to_currency = input("Enter the currency you want to convert to (e.g., EUR): ").upper()

    if from_currency in exchange_rates and to_currency in exchange_rates:
        amount = float(input(f"Enter the amount in {from_currency}: "))
        result = amount * exchange_rates[to_currency] / exchange_rates[from_currency]
        print(f"{amount} {from_currency} is equal to {result} {to_currency}")
    else:
        print("Invalid currencies. Please choose valid options.")

    another = input("Do you want to convert another currency? (yes/no): ").lower()
    if another != "yes":
        print("Thank you for using the Currency Converter!")
        break
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We create a dictionary, exchange_rates, that stores exchange rates relative to the US dollar (USD).</li>
	<li>Inside the program loop, we display the available currencies by iterating through the keys of the exchange_rates dictionary.</li>
	<li>The user is asked to enter the currency they have and the currency they want to convert to.</li>
	<li>We check if the entered currencies are valid, and if so, we ask for the amount to be converted.</li>
	<li>The program calculates the conversion and displays the result.</li>
	<li>The user is given the option to convert another currency, and the loop continues until they decide to exit.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Python Currency Converter. This project has introduced you to dictionaries, user input, and basic arithmetic operations while providing a practical tool for currency conversion.

Whether you're planning an international trip or managing your finances, this Currency Converter is a valuable addition to your Python portfolio. Stay tuned for more exciting Python projects that combine coding and practicality. Happy coding! 🐍✨