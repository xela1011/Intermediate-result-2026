<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JAC Result 2026</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial;
}

body {
  background: #e6e6e6;
}

/* Header */
.topbar {
  background: #8b0000;
  color: white;
  text-align: center;
  padding: 15px;
}

.topbar h1 {
  font-size: 20px;
}

/* Form Container */
.container {
  width: 90%;
  max-width: 360px;
  margin: 30px auto;
  background: #e8dccf;
  border: 2px solid #a00000;
  padding: 25px;
}

.form-box {
  border: 1px solid #888;
  padding: 20px;
  background: #efe3d6;
}

label {
  display: block;
  margin-top: 12px;
  font-weight: bold;
}

input, select {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
}

/* CAPTCHA */
.captcha {
  background: #f3f3f3;
  padding: 10px;
  text-align: center;
  margin: 10px 0;
  font-size: 20px;
  letter-spacing: 4px;
}

/* Buttons */
.button-group {
  display: flex;
  justify-content: space-between;
  margin-top: 15px;
}

button {
  padding: 10px;
  border: none;
  cursor: pointer;
}

.submit-btn {
  background: red;
  color: white;
}

.reset-btn {
  background: darkred;
  color: white;
}

/* FUN SCREEN */
.funny {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: black;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: 30px;
  z-index: 9999;
  animation: fadeIn 0.5s;
}

.emoji {
  font-size: 60px;
  animation: bounce 0.5s infinite alternate;
}

@keyframes bounce {
  from { transform: translateY(0); }
  to { transform: translateY(-20px); }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>

</head>
<body>

<div class="topbar">
  <h1>JHARKHAND ACADEMIC COUNCIL</h1>
  Annual Intermediate Examination - 2026
</div>

<div class="container">
  <div class="form-box">

    <label>ROLL CODE</label>
    <input type="text" id="rollcode">

    <label>ROLL NUMBER</label>
    <input type="text" id="rollnumber">

    <label>STREAM</label>
    <select id="stream">
      <option>--SELECT--</option>
      <option>Science</option>
      <option>Commerce</option>
      <option>Arts</option>
    </select>

    <div class="captcha" id="captchaText">ABC123</div>
    <button onclick="generateCaptcha()">Refresh</button>

    <input type="text" id="captchaInput" placeholder="Enter CAPTCHA">

    <div class="button-group">
      <button class="submit-btn" onclick="submitForm()">Submit</button>
      <button class="reset-btn" onclick="resetForm()">Reset</button>
    </div>

  </div>
</div>

<script>
// Generate CAPTCHA
function generateCaptcha() {
  const chars = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
  let cap = '';
  for (let i = 0; i < 6; i++) {
    cap += chars[Math.floor(Math.random() * chars.length)];
  }
  document.getElementById('captchaText').innerText = cap;
}

// Submit Form (PRANK 😆)
function submitForm() {
  const entered = document.getElementById('captchaInput').value;
  const actual = document.getElementById('captchaText').innerText;

  if (entered !== actual) {
    alert('Wrong CAPTCHA 😂');
    return;
  }

  // Create prank screen
  const div = document.createElement('div');
  div.className = 'funny';

  div.innerHTML = `
    😂 APRIL FOOL 😂
    <div class="emoji">🤡 🤣 😜 🤪</div>
    Got You Bro 😆
  `;

  document.body.appendChild(div);

  // Remove after 5 sec
  setTimeout(() => {
    div.remove();
  }, 5000);
}

// Reset
function resetForm() {
  document.getElementById('rollcode').value = '';
  document.getElementById('rollnumber').value = '';
  document.getElementById('captchaInput').value = '';
  generateCaptcha();
}

// Auto generate captcha on load
generateCaptcha();
</script>

</body>
</html>
