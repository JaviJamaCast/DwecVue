<script setup>
import { ref } from 'vue'

const mensajes = ref([
  { contenido: 'loremIpsum papa' },
  { contenido: 'loremIpsum papa 2' },
  { contenido: 'loremIpsum papa 4' },
  { contenido: 'loremIpsum papa 5' }
])

const editarMensaje = (index) => {
  const nuevoContenido = window.prompt('Editar mensaje:', mensajes.value[index].contenido)
  if (nuevoContenido !== null && nuevoContenido !== '') {
    mensajes.value[index].contenido = nuevoContenido
  }
}
const eliminarMensaje = (index) => {
  const borrar = confirm('Desea borrar el mensaje?')
  if (borrar) {
    mensajes.value.splice(index, 1)
  }
}
</script>

<template>
  <section>
    <h1>Mensajes</h1>
    <h3 v-if="!mensajes.length">No hay mensajes</h3>
    <ul v-else>
      <li v-for="(mensaje, index) in mensajes" :key="mensaje.id" @dblclick="editarMensaje(index)">
        {{ mensaje.contenido }}
        <button @click.stop="eliminarMensaje(index)">Eliminar</button>
      </li>
    </ul>
    <p><small>Haz doble clic en un mensaje para editarlo.</small></p>
  </section>
</template>

<style scoped>
ul {
  list-style: none;
}

li {
  cursor: pointer;
  transition: background-color 0.3s;
}
li:hover {
  background-color: #ffb4b4;
}
button {
  margin-left: 10px;
}
</style>
