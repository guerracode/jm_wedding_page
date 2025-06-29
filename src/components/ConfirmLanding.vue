<script setup>
import { onMounted, ref } from 'vue'
import Title from './sub/SectionTitle.vue'

const loader = ref(false)
const responseSent = ref(false)

const urlSearchParams = new URLSearchParams(window.location.search)
const params = Object.fromEntries(urlSearchParams.entries())
let pases = document.getElementById('pases')
if (pases)
  if (parseInt(params.pases) > 1) pases.innerHTML = params.pases.toString() + ' pases'
  else pases.innerHTML = params.pases.toString() + ' pase'

onMounted(() => {
  document.getElementById('form').addEventListener('submit', function (e) {
    e.preventDefault()
    loader.value = true
    document.getElementById('submit-button').innerHTML = 'Enviando...'
    document.getElementById('submit-button').style.display = 'block'
    document.getElementById('submit-button').disabled = true

    //Collect the form data
    var fromData = new FormData(this)
    var keyValuePairs = []
    for (var pair of fromData.entries()) {
      keyValuePairs.push(pair[0] + '=' + pair[1])
    }

    var formDataString = keyValuePairs.join('&')

    // Send a POST request to your Google Apps Script
    fetch(
      'https://script.google.com/macros/s/AKfycbypulX2GV9jPrmDyk88FNtbpXk-x_aQmMo7xMs0Z6VQ58X8HcZqdpgUw4fgtHAAQ2oYOQ/exec',
      {
        redirect: 'follow',
        method: 'POST',
        body: formDataString,
        headers: {
          'Content-Type': 'text/plain;charset=UTF-8',
        },
      }
    )
      .then((response) => {
        if (response) {
          return response
        } else {
          throw new Error('Failed to submit form.')
        }
      })
      .then(function () {
        loader.value = false
        responseSent.value = true
      })
  })
})
</script>

<template>
  <section v-if="!responseSent" id="Confirmar" class="lg:w-5xl mx-auto pb-20 px-10">
    <Title title="Confirma tu asistencia" />
    <div
      class="max-w-lg mx-auto flex flex-col items-center justify-center mt-10 p-4 text-center border-2 border-jm-primary rounded-4xl"
    >
      <p class="text-xl not-italic mb-4">¡Nos encantaría contar contigo!</p>
      <p class="text-base mb-4">
        Por favor, confirma tu asistencia antes del 5 de Noviembre de 2025.
      </p>
      <p class="text-base mb-4 not-italic">Respetuosamente no niños</p>
      <p class="text-base">Hemos reservado para ti:</p>
      <p id="pases" class="text-xl font-bold underline">1 pase</p>

      <div class="loader my-10" v-if="loader"></div>
      <form v-if="!loader" class="w-full" id="form" method="POST">
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="name" class="text-base mb-2">Nombre:</label>
          <input
            type="text"
            id="name"
            name="Nombre"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          />
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="phone" class="text-base mb-2">Telefono:</label>
          <input
            type="number"
            id="phone"
            name="Telefono"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          />
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="response" class="text-base mb-2">Asistiré:</label>
          <select
            id="response"
            name="Asistire"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          >
            <option value="" disabled selected>Selecciona una opción</option>
            <option value="Si">Sí, asistiré</option>
            <option value="No">No podré asistir</option>
          </select>
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="note" class="text-base mb-2">Nota:</label>
          <textarea
            id="note"
            name="Nota"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
          ></textarea>
        </div>
        <button
          type="submit"
          id="submit-button"
          class="mt-6 border-2 border-jm-primary text-jm-primary py-3 w-full rounded-2xl transition duration-300"
        >
          Confirmar asistencia
        </button>
      </form>
    </div>
  </section>
  <section v-if="responseSent" id="Confirmar" class="lg:w-5xl mx-auto pb-20 px-10">
    <div
      class="max-w-lg mx-auto flex flex-col items-center justify-center mt-10 p-4 text-center border-2 border-jm-primary rounded-4xl"
    >
      <p class="text-3xl">Respuesta enviada exitosamente</p>
      <p class="text-xl mt-5">¡Gracias por confirmar tu asistencia!</p>
    </div>
  </section>
</template>

<style scoped>
.loader {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: transparent;
  border-radius: 50%;
}

.loader {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: transparent;
  width: 36px;
  height: 36px;
}

.loader {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: transparent;
  width: 36px;
  height: 36px;
  animation: spin89345 1s linear infinite;
}

@keyframes spin89345 {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
</style>
