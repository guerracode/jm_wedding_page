<script setup>
import Title from './sub/SectionTitle.vue'
</script>

<template>
  <section id="Galeria" class="lg:w-5xl mx-auto">
    <Title title="Momentos especiales" />
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-4 p-4 justify-items-center">
      <img src="/img/1_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/2_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/3_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/4_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/5_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/6_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/7_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img src="/img/8_jm.jpg" alt="Jessica y Miguel" class="object-cover h-30 md:h-60 w-full" />
      <img
        src="/img/9_jm.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full hidden md:block"
      />
    </div>
  </section>
</template>
