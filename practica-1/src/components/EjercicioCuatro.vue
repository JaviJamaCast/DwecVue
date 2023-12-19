<script setup>
import { ref } from 'vue'
const mensaje = ref('Esto es un mensaje! Hola!')
const mostrar = ref(true)
const mensajeFun = () => {
  mostrar.value = !mostrar.value
}
</script>

<template>
  <button @click="mensajeFun()">Ocultar/mostrar texto</button>
  <small v-if="mostrar">{{ mensaje }}</small>
</template>
