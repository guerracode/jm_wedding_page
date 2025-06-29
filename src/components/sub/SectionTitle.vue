<script setup>
const { title } = defineProps({
  title: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="width-full text-center">
    <h2 class="text-2xl underline underline-offset-3 font-bold">{{ title }}</h2>
  </div>
</template>
