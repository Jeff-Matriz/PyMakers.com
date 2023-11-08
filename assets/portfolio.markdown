---
layout: post
permalink: /jeff/
---
<style>
	img {
		display: block;
		margin-left: auto;
		margin-right: auto;
		width: 150px;
		height: 150px;
		border-radius: 50%;
	}
	input[type=text], select, textarea {
		width: 100%;
		padding: 12px;
		border: 1px solid #ccc;
		border-radius: 4px;
		box-sizing: border-box;
		margin-top: 6px;
		margin-bottom: 16px;
		resize: vertical;
	}

	input[type=email], select, textarea {
		width: 100%;
		padding: 12px;
		border: 1px solid #ccc;
		border-radius: 4px;
		box-sizing: border-box;
		margin-top: 6px;
		margin-bottom: 16px;
		resize: vertical;
	}

	input[type=submit] {
		background-color: #0099ff;
		color: white;
		padding: 12px 20px;
		border: none;
		border-radius: 4px;
		cursor: pointer;
	}

	input[type=submit]:hover {
		background-color: #007acc;
	}

	.form-container {
		border-radius: 5px;
		box-sizing: border-box;
		background-color: #f2f2f2;
		padding: 20px;
	}
</style>
<img src="/assets/profile.png" alt="Profile photo"><br>

**About Me**

Welcome to my website, where we're all about making Python accessible and exciting for beginners! I'm a Python enthusiast and web developer proudly based in the Philippines. Here, I'm dedicated to simplifying the world of coding and guiding newcomers through their first steps in Python. With a focus on beginner projects, I'll help you embark on your coding journey and discover the joy of creating with Python, one project at a time. Let's explore this incredible world of possibilities together, and turn our Python dreams into reality!

**Contact Me**

Thank you for visiting my website, and I look forward to sharing my journey and expertise with you.  If you want to get in touch, please feel free to send me a message here:
<br>
<div class="form-container">
  <form id="contact-form">
    <label for="name">Name</label>
    <input type="text" id="name" name="name" placeholder="Your name.." required>
    <label for="email">Email</label>
    <input type="email" id="email" name="email" placeholder="Your email address.." required>
    <label for="subject">Subject</label>
    <textarea id="subject" name="subject" placeholder="Write something.." style="height:200px"></textarea>
    <input type="submit" value="Submit">
  </form>
</div>

[contact]: https://pymakers.com/contact
[gh]: https://github.com/Jeff-Matriz

<script src="https://cdn.emailjs.com/dist/email.min.js"></script>
<script>
  emailjs.init("5MEZZVWVxcnC0nGzv");

  document.getElementById("contact-form").addEventListener("submit", function (event) {
    event.preventDefault(); // Prevent the default form submission

    // Send the email using EmailJS
    emailjs.sendForm("service_6mwmmmj", "template_hftow3f", this).then(
      function (response) {
        alert("Message sent successfully!");
        // Redirect or perform any other action here after successful submission.
      },
      function (error) {
        alert("Failed to send message. Please try again later.");
        console.error("EmailJS error:", error);
      }
    );
  });
</script>