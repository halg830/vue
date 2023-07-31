<script setup>
import { ref } from 'vue'

let producto = ref({})

let data = ref([])

const agregar = () => {  
  data.value.push({ ...producto.value })
}




</script>

<template>
  <div>
    <!-- 5 cajas = codigo, nombreproducto, precio a como se vende, cantidad, costo a como me lo venden 
   button agregar añadir a un vector 
   pintar en una tabla el vector
   if la cantidad de un producto es menor a 10 unidades coloca de rojo
   else if mayor a 50 unidades azul
   else negro
   -->

    <label for="">Código: <input type="text" v-model="producto.codigo"></label>
    <label for="">Producto: <input type="text" v-model="producto.nombre"></label>
    <label for="">Costo:<input type="number" v-model="producto.costo"></label>
    <label for="">Cantidad: <input type="number" v-model="producto.cantidad"></label>
    <label for="">Precio: <input type="number" v-model="producto.precio"></label>
    <button @click="agregar()">Enviar</button>

    <table>
      <tr>
        <td>Codigo</td>
        <td>Nombre</td>
        <td>Precio</td>
        <td >Cantidad</td>
        <td>Cargo</td>
      </tr>

      <tr v-for="(item, index) in data" :key="index">
        <td>{{ item.codigo }}</td>
        <td>{{ item.nombre }}</td>
        <td>{{ item.costo }}</td>
        <td :style="item.cantidad<10 ? 'color: red': item.cantidad>50 ? 'color: blue;' : 'color : black;'">{{ item.cantidad }}</td>
        <td>{{ item.precio }}</td>
      </tr>

    </table>
  </div>
</template>

<style scoped></style>
