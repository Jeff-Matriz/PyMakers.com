---
title:  "Crunch Numbers with Fun - Building a Basic Calculator with Kivy"
date:   2023-10-10
---

<style>
    img { 
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 300px;       
    height: 400px;
    border-radius: 8px;
    }
</style>

Welcome back to PyMakers, where we make coding an enjoyable experience. In this project, we're about to embark on an adventure into the world of mobile app development. Specifically, we'll create a "Basic Calculator" using the powerful Kivy framework. Whether you're new to app development or a seasoned coder, this project is both fun and educational.

**Why a Basic Calculator?**

Calculators are an everyday tool, and building one offers a fantastic learning experience. It allows you to understand the essentials of user interfaces, event handling, and basic operations. Plus, the skills you'll gain are easily transferrable to more complex app development.

**The Kivy Framework**

Kivy is a Python framework that's a game-changer for mobile app development. Its cross-platform compatibility makes it a standout choice. You can create applications for Android, iOS, Windows, and more, all with a single codebase. Kivy's open-source nature encourages a strong developer community, making it ideal for learners and pros alike.

**The Python Code**

Let's dive into the Python code for our Basic Calculator:

```python
from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.button import Button
from kivy.uix.textinput import TextInput
from kivy.uix.label import Label

class CalculatorApp(App):
    def build(self):
        self.operators = ["/", "*", "+", "-"]
        self.last_was_operator = None
        self.last_button = None
        main_layout = BoxLayout(orientation="vertical")
        self.solution = TextInput(
            multiline=False, readonly=True, halign="right", font_size=55
        )
        main_layout.add_widget(self.solution)
        buttons = [
            ["7", "8", "9", "/"],
            ["4", "5", "6", "*"],
            ["1", "2", "3", "-"],
            [".", "0", "C", "+"],
        ]
        for row in buttons:
            h_layout = BoxLayout()
            for label in row:
                button = Button(
                    text=label,
                    pos_hint={"center_x": 0.5, "center_y": 0.5},
                )
                button.bind(on_press=self.on_button_press)
                h_layout.add_widget(button)
            main_layout.add_widget(h_layout)

        equals_button = Button(
            text="=",
            pos_hint={"center_x": 0.5, "center_y": 0.5},
        )
        equals_button.bind(on_press=self.on_solution)
        main_layout.add_widget(equals_button)

        return main_layout

    def on_button_press(self, instance):
        current = self.solution.text
        button_text = instance.text

        if current and (self.last_was_operator and button_text in self.operators):
            return
        new_text = current + button_text
        self.solution.text = new_text

    def on_solution(self, instance):
        text = self.solution.text
        try:
            solution = str(eval(self.solution.text))
            self.solution.text = solution
        except Exception:
            self.solution.text = "Error"

if __name__ == "__main__":
    app = CalculatorApp()
    app.run()
```

This is the output:

<img src="/assets/calculator.png" alt="Kivy calculator" class="calc">

**How it Works**

Our Basic Calculator app consists of a Kivy interface with numeric buttons, basic operations, and an equals button for calculating the result. It accepts user input and evaluates the expression when the equals button is pressed. The solution is then displayed in the input field.

This project not only introduces you to the Kivy framework but also covers UI layout, button interactions, and basic mathematical operations. It's a great way to get hands-on experience with mobile app development.

**Conclusion**

Congratulations! You've just created your first Android app with Python and Kivy. This Basic Calculator is a small step towards more exciting and complex app development. Stay tuned for more PyMakers projects that bring coding to life, one fun project at a time. Happy coding and calculating! 🐍🧮

<br>In the upcoming blog, I'll guide you on creating an APK installer for this calculator app, so stay tuned!