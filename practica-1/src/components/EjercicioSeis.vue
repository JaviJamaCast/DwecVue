<script setup>
import { ref } from 'vue'
const texto1 = ref('')
const texto2 = ref('')
</script>

<template>
  <div>
    <label for="nombre">Ingrese su nombre:</label>
    <input id="nombre" type="text" v-model="texto1" />

    <label for="apellido">Ingrese su apellido:</label>
    <input id="apellido" type="text" v-model="texto2" />

    <small v-if="texto1.length > 0 && texto2.length > 0"> Ambos textos llenos </small>
    <small v-else> Completa los textos! </small>
  </div>
</template>

<style scoped>
div{
  display: flex;
  flex-direction: column;
}
</style>