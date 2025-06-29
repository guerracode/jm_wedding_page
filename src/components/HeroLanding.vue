<script setup>
// Set the date we're counting down to
var countDownDate = new Date('March 21, 2026 13:00:00').getTime()

// Update the count down every 1 second
var x = setInterval(function () {
  // Get today's date and time
  var now = new Date().getTime()

  // Find the distance between now and the count down date
  var distance = countDownDate - now

  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24))
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
  var seconds = Math.floor((distance % (1000 * 60)) / 1000)

  // Display the result in the element
  const daysElem = document.getElementById('days')
  if (daysElem) daysElem.innerHTML = days.toString()
  const hoursElem = document.getElementById('hours')
  if (hoursElem) hoursElem.innerHTML = hours.toString()
  const minutesElem = document.getElementById('minutes')
  if (minutesElem) minutesElem.innerHTML = minutes.toString()
  const secondsElem = document.getElementById('seconds')
  if (secondsElem) secondsElem.innerHTML = seconds.toString()

  // If the count down is finished, write some text
  if (distance < 0) {
    clearInterval(x)
    if (daysElem) daysElem.innerHTML = '0'
    if (hoursElem) hoursElem.innerHTML = '0'
    if (minutesElem) minutesElem.innerHTML = '0'
    if (secondsElem) secondsElem.innerHTML = '0'
  }
}, 1000)
</script>

<template>
  <section class="relative">
    <div class="hero flex flex-col items-center justify-between p-6 text-jm-secondary">
      <div class="text-center mt-10">
        <h1 class="text-4xl italic font-bold">Jessica & Miguel</h1>
        <h3 class="text-xl mt-3 italic">21 Marzo 2026</h3>
      </div>
      <div class="flex items-center justify-center">
        <div class="flex flex-col items-center justify-between m-3">
          <p class="text-2xl" id="days">310</p>
          <p class="text-xl italic">Dias</p>
        </div>
        <div class="flex flex-col items-center justify-between m-3">
          <p class="text-2xl" id="hours">15</p>
          <p class="text-xl">Hrs</p>
        </div>
        <div class="flex flex-col items-center justify-between m-3">
          <p class="text-2xl" id="minutes">20</p>
          <p class="text-xl">Min</p>
        </div>
        <div class="flex flex-col items-center justify-between m-3">
          <p class="text-2xl" id="seconds">10</p>
          <p class="text-xl">Seg</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
section .hero {
  height: calc(100vh - 64px);
  display: flex;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.3) 0%, rgba(0, 0, 0, 0.3) 100%),
    url('../../public/background_hero.jpg') lightgray 50% / cover no-repeat;
  background-position: center;
  background-position-x: 38%;
}
</style>
