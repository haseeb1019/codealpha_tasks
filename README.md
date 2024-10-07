<!DOCTYPE html>
<html>
<head>
  <title>Age Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      text-align: center;
      padding: 50px;
    }
    input, button {
      padding: 10px;
      margin: 10px;
      border-radius: 5px;
    }
  </style>
</head>
<body>

<h1>Age Calculator</h1>

<label for="birthdate">Enter your birthdate:</label>
<input type="date" id="birthdate" />

<br>

<button onclick="calculateAge()">Calculate Age</button>

<h2 id="ageDisplay"></h2>

<script>
function calculateAge() {
  const birthdate = new Date(document.getElementById('birthdate').value);
  const today = new Date();
  let age = today.getFullYear() - birthdate.getFullYear();
  const monthDifference = today.getMonth() - birthdate.getMonth();

  if (monthDifference < 0 || (monthDifference === 0 && today.getDate() < birthdate.getDate())) {
    age--;
  }

  document.getElementById('ageDisplay').textContent = `Your age is: ${age} years`;
}
</script>

</body>
</html>
