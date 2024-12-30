<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>New Year Wishes</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 20px;
    }
    input {
      padding: 10px;
      margin: 10px;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h1>🎉 Happy New Year! 🎉</h1>
  <p>Enter your name to receive personalized New Year wishes!</p>
  <form id="wishForm">
    <input type="text" id="name" placeholder="Enter your name" required>
    <button type="submit">Submit</button>
  </form>
  <div id="response" style="margin-top: 20px;"></div>

  <script>
    document.getElementById("wishForm").addEventListener("submit", function (e) {
      e.preventDefault();
      const name = document.getElementById("name").value;
      
      // Save name using fetch API or send to the server
      fetch('https://your-server-link.com/save', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ name })
      }).then(response => response.json())
        .then(data => {
          document.getElementById("response").innerHTML = `Thank you, ${name}! Your New Year wish has been saved! 🎉`;
        }).catch(error => {
          document.getElementById("response").innerHTML = `Oops, something went wrong. Please try again.`;
          console.error(error);
        });
    });
  </script>
</body>
</html>
