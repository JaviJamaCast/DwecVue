<script setup>
import { ref } from 'vue'

// ref de un objeto. Tambi´en se puede con reactive.
let cabecera = ref({
  titulo: 'Practica con v-bind',
  cuerpo: 'Este es un ejemplo practico con v-bind en Vue 3',
  color: 'red',
  link: 'https://www.google.com/',
  activado: false
})

const estiloAzulCeleste = {
  color: 'cyan',
  'text-decoration': 'none'
}

const estiloVerde = {
  color: 'green ',
  'text-decoration': 'none'
}
</script>

<template>
  <header>
    <h1>{{ cabecera.titulo }}</h1>
  </header>
  <p v-bind:class="{ cuerpo: cabecera.color != 'red' ? false : true }">{{ cabecera.cuerpo }}</p>
  <a :href="cabecera.link" :style="cabecera.activado ? estiloAzulCeleste : estiloVerde"
    >Ir a google</a
  >
</template>

<style scoped>
.cabecera {
  text-decoration: line-through;
  color: red;
}
.cuerpo {
  color: blue;
}
</style>
