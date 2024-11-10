<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Countdown Timer</title>

</head>

<body>

<h1>Countdown Timer</h1>

 <label for="minutes">Enter Minutes: </label>

<input type="number" id="minutes" placeholder="Enter minutes">

<button onclick="startTimer()">Start Countdown</button>

<div class="timer" id="timerDisplay">00:00</div>

<script> let countdown;

function startTimer() {

clearInterval(countdown);

const minutesInput = document.getElementById('minutes').value;

let time = minutesInput * 60; 

countdown = setInterval(() => {

const minutes = Math.floor(time / 60);

const seconds = time % 60;

document.getElementById('timerDisplay').innerHTML = `${minutes < 10 ? '0' : ''}

${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;

if (time <= 0) {
  clearInterval(countdown);

document.getElementById('timerDisplay').innerHTML = "Time's up!";

}

time--;

}, 1000);

}

</script>

</body>

</html>
