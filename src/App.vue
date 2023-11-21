<script setup>
import { RouterView } from 'vue-router'
import NavBar from '../src/components/NavBar.vue'
</script>

<template>
  <section>
    <NavBar />
  </section>

  <RouterView />
</template>

<style scoped></style>
