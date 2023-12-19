<script setup>
import { ref } from 'vue'

const tareas = ref([
  { descripcion: 'Hacer la compra', completada: false },
  { descripcion: 'Lavar la ropa', completada: false },
  { descripcion: 'Pega la puñalada socio', completada: false },
  { descripcion: 'Meter vicio', completada: true }
])

const tareasFun = (index) => {
  if (!tareas.value[index].completada) {
    tareas.value[index].completada = true
  } else {
    tareas.value.splice(index, 1)
  }
}
</script>

<template>
  <section>
    <h1>Tareas</h1>
    <h3 v-show="!tareas.length">No hay tareas</h3>
    <ul v-show="tareas.length">
      <li v-for="(tarea, index) in tareas" :key="index" @dblclick="tareasFun(index)">
        {{ tarea.descripcion }}: {{ tarea.completada ? 'Completada' : 'Pendiente' }}
      </li>
    </ul>
  </section>
</template>

<style scoped>
ul {
  list-style: none;
}
li:hover {
  cursor: pointer;
}
</style>
