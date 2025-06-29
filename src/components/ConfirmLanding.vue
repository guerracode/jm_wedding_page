<script setup>
const urlSearchParams = new URLSearchParams(window.location.search)
const params = Object.fromEntries(urlSearchParams.entries())
let pases = document.getElementById('pases')
if (pases)
  if (parseInt(params.pases) > 1) pases.innerHTML = params.pases.toString() + ' pases'
  else pases.innerHTML = params.pases.toString() + ' pase'
</script>

<template>
  <section id="Confirmar" class="lg:w-5xl mx-auto pb-20 px-10">
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

      <form class="w-full" method="POST">
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="name" class="text-base mb-2">Nombre:</label>
          <input
            type="text"
            id="name"
            name="name"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          />
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="phone" class="text-base mb-2">Telefono:</label>
          <input
            type="number"
            id="phone"
            name="phone"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          />
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="response" class="text-base mb-2">Asistiré:</label>
          <select
            id="response"
            name="response"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          >
            <option value="" disabled selected>Selecciona una opción</option>
            <option value="yes">Sí, asistiré</option>
            <option value="no">No podré asistir</option>
          </select>
        </div>
        <div class="flex flex-col items-start justify-center mt-4">
          <label for="note" class="text-base mb-2">Nota:</label>
          <textarea
            id="note"
            name="note"
            class="border-2 border-jm-primary rounded-lg p-2 w-full focus:border-amber-950 focus:outline-none"
            required
          ></textarea>
        </div>
        <button
          type="submit"
          class="mt-6 border-2 border-jm-primary text-jm-primary py-3 w-full rounded-2xl transition duration-300"
        >
          Confirmar asistencia
        </button>
      </form>
    </div>
  </section>
</template>
