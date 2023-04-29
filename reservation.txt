// Check if any reservations exist in localStorage
let reservations = JSON.parse(localStorage.getItem('reservations')) || [];

// Function to add a new reservation to the array and localStorage
function addReservation(name, email, phone, date, time, partySize, specialRequests) {
  const newReservation = {
    name: name,
    email: email,
    phone: phone,
    date: date,
    time: time,
    partySize: partySize,
    specialRequests: specialRequests
  };

  reservations.push(newReservation);
  localStorage.setItem('reservations', JSON.stringify(reservations));
}

// Function to display all reservations in the array
function displayReservations() {
  const reservationList = document.getElementById('reservation-list');
  reservationList.innerHTML = '';

  reservations.forEach(function(reservation) {
    const listItem = document.createElement('li');
    listItem.innerHTML = `
      <strong>${reservation.name}</strong> - ${reservation.email} - ${reservation.phone} - ${reservation.date} - ${reservation.time} - ${reservation.partySize} - ${reservation.specialRequests}
    `;
    reservationList.appendChild(listItem);
  });
}

// Call the displayReservations function on page load
displayReservations();

// Add event listener to form submit button
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

  // Call the addReservation function with the form data
  addReservation(name, email, phone, date, time, partySize, specialRequests);

  // Call the displayReservations function to update the reservation list
  displayReservations();

  // Clear the form fields
  form.reset();
});