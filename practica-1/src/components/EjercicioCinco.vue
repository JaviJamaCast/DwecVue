<script setup>
import { ref } from 'vue'
const listaAnimales = ref(['Lobo', 'Zorro', 'Gato', 'Nea'])
//listaAnimales.value = []
</script>

<template>
  <section>
    <h1>Animales</h1>
    <h2 v-if="!listaAnimales.length">No hay elementos</h2>
    <ul>
      <li v-for="(animal, index) in listaAnimales" :key="index">
        {{ animal }}
      </li>
    </ul>
  </section>
</template>

<style scoped>
ul {
  list-style: none;
}
</style>
