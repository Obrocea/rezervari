<!DOCTYPE html>
<html>
<head>
	<title>Reservation Form</title>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<style>
		form {
			margin: 0 auto;
			max-width: 600px;
			padding: 20px;
			background-color: #f2f2f2;
			border-radius: 5px;
			box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
			font-family: Arial, sans-serif;
		}
		input[type=text], input[type=date], select, textarea {
			width: 100%;
			padding: 12px;
			border: 1px solid #ccc;
			border-radius: 4px;
			resize: vertical;
		}
		input[type=submit] {
			background-color: #4CAF50;
			color: white;
			padding: 12px 20px;
			border: none;
			border-radius: 4px;
			cursor: pointer;
		}
		input[type=submit]:hover {
			background-color: #45a049;
		}
	</style>
</head>
<body>
	<h1>Reservation Form</h1>
	<form>
		<label for="name">Name:</label>
		<input type="text" id="name" name="name" placeholder="Enter your name">

		<label for="email">Email:</label>
		<input type="text" id="email" name="email" placeholder="Enter your email">

		<label for="phone">Phone:</label>
		<input type="text" id="phone" name="phone" placeholder="Enter your phone number">

		<label for="date">Date:</label>
		<input type="date" id="date" name="date">

		<label for="time">Time:</label>
		<input type="time" id="time" name="time">

		<label for="party-size">Party Size:</label>
		<select id="party-size" name="party-size">
			<option value="1">1</option>
			<option value="2">2</option>
			<option value="3">3</option>
			<option value="4">4</option>
			<option value="5">5</option>
			<option value="6">6</option>
			<option value="7">7</option>
			<option value="8">8</option>
			<option value="9">9</option>
			<option value="10+">10+</option>
		</select>

		<label for="special-requests">Special Requests:</label>
		<textarea id="special-requests" name="special-requests" placeholder="Enter any special requests here"></textarea>

		<input type="submit" value="Submit">
	</form>

	<script>
		const form = document.querySelector('form');
		form.addEventListener('submit', function(event) {
			event.preventDefault();
			const name = document.getElementById('name').value;
			const email = document.getElementById('email').value;
			const phone = document.getElementById('phone').value;
			const date = document.getElementById('date').value;
			const time = document.getElementById('time').value;
			const partySize = document.getElementById('party-size').value;
			const specialRequests = document.getElementById('special-requests').value;

			// TODO: Send reservation data to server using AJAX or