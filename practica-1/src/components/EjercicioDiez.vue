<script setup>
import { ref } from 'vue'

const cesta = ref([])
const productos = ref(['Papa', 'Yuca', 'Pera', 'Ajo'])
const selected = ref('Yuca')

const guardarCesta = () => {
  const productoEnCesta = cesta.value.find((item) => item.producto === selected.value)
  if (!productoEnCesta) {
    cesta.value.push({ producto: selected.value, unidades: 1 })
  } else {
    alert('Producto ya agregado')
  }
}

const masUnidades = (index) => {
  cesta.value[index].unidades++
}

const menosUnidades = (index) => {
  if (cesta.value[index].unidades > 1) {
    cesta.value[index].unidades--
  }
}

const eliminarProd = (index) => {
  const borrar = confirm('¿Desea borrar el producto?')
  if (borrar) {
    cesta.value.splice(index, 1)
  }
}
</script>

<template>
  <section>
    <h1>Cesta</h1>
    <h3 v-if="!cesta.length">No hay productos</h3>
    <ul v-else>
      <li v-for="(prod, index) in cesta" :key="index">
        {{ prod.producto }}: {{ prod.unidades }}
        <button @click="masUnidades(index)">+</button>
        <button @click="menosUnidades(index)" :disabled="prod.unidades === 1">-</button>
        <button @click="eliminarProd(index)">Eliminar</button>
      </li>
    </ul>
    <label for="producto-selector">Elige un producto:</label>
    <select v-model="selected" id="producto-selector">
      <option v-for="(prod, index) in productos" :key="index">{{ prod }}</option>
    </select>
    <button @click="guardarCesta">Agregar a la cesta</button>
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
