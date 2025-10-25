<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Seminar Registration Form</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background: linear-gradient(135deg, #6dd5ed, #2193b0);
      color: #333;
      margin: 0;
      padding: 0;
    }
    .container {
      background: #fff;
      padding: 20px;
      max-width: 400px;
      width: 90%;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }
    input,
    textarea {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
      box-sizing: border-box;
    }
    button {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
      background: #007bff;
      color: #fff;
      transition: opacity 0.3s;
    }
    button:hover {
      opacity: 0.9;
    }
    @media (max-width: 480px) {
      .container {
        padding: 15px;
      }
    }
  </style>
</head>
<body>
  <form class="container" id="registrationForm" action="https://formsubmit.co/mubarakmehdi7@gmail.com" method="POST">
    <h2>REGISTRATION FOR SEMINAR</h2>

    <label for="name">Full Name</label>
    <input type="text" id="name" name="Full Name" required />

    <label for="email">Email</label>
    <input type="email" id="email" name="Email" required />

    <label for="phone">Phone Number</label>
    <input type="tel" id="phone" name="Phone" required />

    <label for="college">College Name</label>
    <input type="text" id="college" name="College" required />

    <!-- Optional: hidden input to avoid spam -->
    <input type="hidden" name="_captcha" value="false" />
    <input type="hidden" name="_template" value="table" />

    <button type="submit">Submit</button>
  </form>

  <script>
    const form = document.getElementById('registrationForm');

    form.addEventListener('submit', async (e) => {
      e.preventDefault(); // prevent default page reload

      const formData = new FormData(form);

      try {
        const response = await fetch(form.action, {
          method: 'POST',
          body: formData,
          headers: {
            'Accept': 'application/json',
          },
        });

        if (response.ok) {
          alert('✅ Registration successful! Check your email for confirmation.');
          form.reset();
        } else {
          alert('❌ Submission failed. Please try again.');
        }
      } catch (error) {
        alert('❌ Network error. Please check your internet connection.');
      }
    });
  </script>
</body>
</html>
