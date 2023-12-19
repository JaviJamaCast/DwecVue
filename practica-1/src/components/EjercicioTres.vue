<script setup>
import { ref } from 'vue'
const texto = ref('Texto por default')
</script>

<template>
  <h1 v-if="texto.length">Texto: {{ texto }}</h1>
  <h1 v-else>Escribe cualquier cosa!</h1>
  <p>Ingrese su texto : <textarea v-model="texto"></textarea></p>
  <small v-if="texto.length"> Longitud del mensaje: {{ texto.length }} </small>
</template>
