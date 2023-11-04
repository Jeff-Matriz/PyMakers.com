---
layout: page
title: Contact
permalink: /contact/
---
<style>
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
<h4>Have a question or feedback? Send me a message!</h4>

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