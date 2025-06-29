<script setup>
import Title from './sub/SectionTitle.vue'
</script>

<template>
  <section id="Vestimenta" class="lg:w-5xl mx-auto">
    <Title title="Vestimenta" />
    <div class="flex flex-col items-center justify-center mt-10 px-10 text-center">
      <img src="/img/clothes.png" alt="clothes" />
      <p class="my-4 text-xl not-italic">Etiqueta formal</p>
      <p class="text-base mb-2"><span class="font-bold">Mujeres:</span> Vestido largo.</p>
      <p class="text-base mb-3">
        Queremos un dia lleno de color y alegría, les pedimos evitar el color
        <span class="underline">negro</span>, para acompañarnos con luz y vida en este momento tan
        especial.
      </p>
      <p class="text-base"><span class="font-bold">Hombres:</span> Traje y corbata.</p>
    </div>
  </section>
</template>
