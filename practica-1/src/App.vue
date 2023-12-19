<script setup>
import EjercicioUnoVue from './components/EjercicioUno.vue'
import EjercicioDos from './components/EjercicioDos.vue'
import EjercicioTres from './components/EjercicioTres.vue'
import EjercicioCuatro from './components/EjercicioCuatro.vue'
import EjercicioCinco from './components/EjercicioCinco.vue'
import EjercicioSeis from './components/EjercicioSeis.vue'
import EjercicioSiete from './components/EjercicioSiete.vue'
import EjercicioOcho from './components/EjercicioOcho.vue'
import EjercicioNueve from './components/EjercicioNueve.vue'
import EjercicioDiez from './components/EjercicioDiez.vue'
</script>

<template>
  <main>
    <div class="grid-item"><EjercicioUnoVue></EjercicioUnoVue></div>
    <div class="grid-item"><EjercicioDos></EjercicioDos></div>
    <div class="grid-item"><EjercicioTres></EjercicioTres></div>
    <div class="grid-item"><EjercicioCuatro></EjercicioCuatro></div>
    <div class="grid-item"><EjercicioCinco></EjercicioCinco></div>
    <div class="grid-item"><EjercicioSeis></EjercicioSeis></div>
    <div class="grid-item"><EjercicioSiete></EjercicioSiete></div>
    <div class="grid-item"><EjercicioOcho></EjercicioOcho></div>
    <div class="grid-item"><EjercicioNueve></EjercicioNueve></div>
    <div class="grid-item"><EjercicioDiez></EjercicioDiez></div>
  </main>
</template>

<style scoped>
main {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 2em;
}
.grid-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid black;
}
</style>
