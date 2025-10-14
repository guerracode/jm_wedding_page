<script setup>
import Title from './sub/SectionTitle.vue'
</script>

<template>
  <section id="Galeria" class="lg:w-5xl mx-auto">
    <Title title="Momentos especiales" />
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-4 p-4 justify-items-center">
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/1_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
      />
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/2_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      />
      <!-- <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/3_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      /> -->
      <!-- <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/4_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      /> -->
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/5_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      />
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/6_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      />
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/7_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      />
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/8_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full"
        loading="lazy"
      />
      <img
        src="https://jessymike.s3.us-east-2.amazonaws.com/9_jm-min.jpg"
        alt="Jessica y Miguel"
        class="object-cover h-30 md:h-60 w-full hidden md:block"
        loading="lazy"
      />
    </div>
  </section>
</template>
