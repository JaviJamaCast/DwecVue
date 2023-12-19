<script setup>
import { ref } from 'vue'
const nombre = ref()
const apellidos = ref()
</script>

<template>
  <h1>Tu nombre completo es: {{ nombre }} {{ apellidos }}</h1>
  <p>Ingrese su nombre : <input type="text" v-model="nombre" /></p>
  <p>Ingrese su apellido : <input type="text" v-model="apellidos" /></p>
</template>
