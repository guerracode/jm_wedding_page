<script setup>
import MenuLanding from './components/MenuLanding.vue'
import HeroLanding from './components/HeroLanding.vue'
import MessageLanding from './components/MessageLanding.vue'
import SectionDivider from './components/sub/SectionDivider.vue'
import GaleryLanding from './components/GaleryLanding.vue'
import EventLanding from './components/EventLanding.vue'
import PresentsLanding from './components/PresentsLanding.vue'
import VestimentLanding from './components/VestimentLanding.vue'
import ConfirmLanding from './components/ConfirmLanding.vue'
</script>

<template>
  <header>
    <MenuLanding />
  </header>

  <main>
    <HeroLanding />
    <MessageLanding />
    <SectionDivider />
    <EventLanding />
    <SectionDivider />
    <VestimentLanding />
    <SectionDivider />
    <GaleryLanding />
    <SectionDivider />
    <PresentsLanding />
    <SectionDivider />
    <ConfirmLanding />
  </main>
</template>

<style scoped>
</style>
