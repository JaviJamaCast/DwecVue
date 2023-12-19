<script setup>
import { ref } from 'vue'
const numero = ref(0)

const incrementar = () => {
  numero.value++
}

const decrementar = () => {
  numero.value--
}
</script>

<template>
  <h2>{{ numero }}</h2>
  <small v-if="numero === 0">El número es igual a 0</small>
  <small v-else-if="numero > 0">El contador es positivo</small>
  <small v-else>El contador es negativo</small>
  <div>
    <button @click="incrementar" aria-label="Incrementar">Incrementar</button>
    <button @click="decrementar" aria-label="Decrementar">Decrementar</button>
  </div>
</template>

<style scoped></style>
