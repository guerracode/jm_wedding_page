<script setup>
import Title from './sub/SectionTitle.vue'
import Itinerary from './sub/EventItinerary.vue'
import Location from './sub/EventLocation.vue'
import Divider from './sub/SectionDivider.vue'
</script>

<template>
  <section id="Evento" class="lg:w-5xl mx-auto mt-5">
    <Title title="Itinerario" />
    <Itinerary />
    <Divider />
    <Title title="Ubicación" />
    <Location />
  </section>
</template>
