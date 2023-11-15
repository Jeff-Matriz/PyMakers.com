---
title: "Build and Deploy a Web Application: PNG to WebP Converter Using Flask, GitHub and Render"
date: 2023-11-15
---

Welcome to this step-by-step guide on creating a simple web app using Flask to convert PNG images to WebP format. In this tutorial, we'll walk through the directory structure, HTML code, Python script, and deployment steps to make it easy for you to follow along.

If you're interested in testing out the completed project, click on this link: <a href="https://png-web-converter.onrender.com" target="_blank"><strong>PyMakers: PNG to WebP Converter</strong></a>

#### Directory Structure

Firstly, let's take a look at the directory structure you'll set up for this project:

```
FlaskWebPConverter/
|-- venv/
|-- templates/
|   |-- index.html
|-- app.py
|-- requirements.txt
```

- **`venv/`**: This folder contains your virtual environment, isolating your project's dependencies.
- **`templates/`**: This folder holds HTML templates. In this case, we have a single template, `index.html`.
- **`app.py`**: This is the main Python script containing your Flask application.
- **`requirements.txt`**: This file lists the Python packages and their versions required for your application.
- **`render.yaml`**: This configuration file specifies how to build and run your app on the Render platform.

#### HTML Form for Image Upload

The HTML file, `index.html`, sets up a simple form for users to upload PNG images:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PNG to WebP Converter</title>
</head>
<body>
    <h1>Upload PNG Image</h1>
    <form action="/convert" method="post" enctype="multipart/form-data">
        <input type="file" name="file" accept=".png">
        <button type="submit">Convert to WebP</button>
    </form>
</body>
</html>
```

This form allows users to select a PNG file for conversion.

#### Flask App for Image Conversion

Now, let's dive into the Flask app, `app.py`. This script handles the image conversion process:

```python
from flask import Flask, render_template, request, send_file
from PIL import Image
from io import BytesIO

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/convert', methods=['POST'])
def convert():
    if 'file' not in request.files:
        return "No file part"

    file = request.files['file']

    if file.filename == '':
        return "No selected file"

    if file:
        try:
            # Convert PNG to WebP
            img = Image.open(file)
            webp_data = BytesIO()
            img.save(webp_data, format='WEBP')
            webp_data.seek(0)

            # Return the WebP file
            return send_file(webp_data, mimetype='image/webp', as_attachment=True, download_name='converted.webp')

        except Exception as e:
            return f"Error converting image: {str(e)}"

if __name__ == '__main__':
    app.run(debug=True)
```

This Flask app sets up routes for rendering the HTML form and handling the image conversion. It uses the Pillow library for image processing and sends back the converted WebP file to the user.

#### Requirements.txt and Dependencies

In the `requirements.txt` file, we specify the Python packages required for our app:

```
Flask==2.2.5
Pillow==9.5.0
gunicorn==21.2.0
```

These packages ensure that your app has the necessary dependencies to run successfully.

### Deployment on Render.com

Now that you've successfully built your Flask app, let's deploy it on Render.com. The process involves creating an account, connecting your GitHub repository, and deploying your app.

1. **Sign up on Render.com**: If you don't have an account, sign up on [Render](https://render.com/).

2. **Create a new web service on Render**:
   - Log in to Render.
   - Click on the "+" button to create a new web service.
   - Choose "Web Service" as the type.

3. **Configure your web service**:
   - Connect your GitHub repository to Render.
   - Specify the name of your app.
   - Set the environment to "Python3".

4. **Add a start command**:
   - In the Start Command section, enter the command to run your Flask app:

     ```bash
     gunicorn app:app
     ```

5. **Deploy your app**:
   - Click the "Create Web Service" button to deploy your app.

6. **Monitor the deployment**:
   - Render will automatically build and deploy your app. You can monitor the progress in the dashboard.

7. **Access your deployed app**:
   - Once the deployment is complete, Render will provide you with a URL. Click on it to access your live web app.

Congratulations! Your Flask app is now deployed on Render.com. The simplicity of Render's interface and the seamless integration with GitHub make it a user-friendly platform for deploying web applications. Feel free to explore Render's additional features for scaling and managing your app as needed.