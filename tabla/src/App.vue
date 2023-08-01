<script setup>
import { ref } from 'vue'

let estado = 0

let producto = ref({
  codigo: "",
  nombre: "",
  costo: 0,
  cantidad: 0,
  precio: 0
})

let data = ref([{
  codigo: "sdfsdfsd",
    nombre: "dsfsdfsd",
    costo: 23324,
    cantidad: 2,
    precio:324
}])

const validar = () =>{
  const errores = []

  Object.values(producto.value).forEach((e) => {
    if (e == "" || e == 0) errores.push({ id: "cuadros", error: "vacios" })
  })
  if (errores.length > 0) return false
  else return true

}

const agregar = (codigo) => {
  if(validar()){
    if(estado==0){
      data.value.push({ ...producto.value })
      producto.value = ref({})
    }
    else {
      
    }

  }

}

const getColor = (item) => {
  if (item < 10) return { color: "red" }
  else if (item > 50) return { color: "blue" }
  else return { color: "black" }
}

const editar = (item) => {
  estado = 1
  producto.value = {
    codigo: item.codigo,
    nombre: item.nombre,
    costo: item.costo,
    cantidad: item.cantidad,
    precio: item.precio
  }
}

const crear = ()=>{
  estado = 0
}

const eliminar = (i) => {
  data.value.splice(i, 1)
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

    <div style="display: flex; justify-content: end;width: 90%;">
      <button @click="crear()" style="margin: 20px 0px;" data-bs-toggle="modal" data-bs-target="#exampleModal">Nuevo
        Usuario</button>
    </div>


    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Formulario</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <p>Código: </p><input type="text" v-model="producto.codigo">
            <p>Producto: </p><input type="text" v-model="producto.nombre">
            <p>Costo: </p><input type="number" v-model="producto.costo">
            <p>Cantidad: </p><input type="number" v-model="producto.cantidad">
            <p>Precio: </p><input type="number" v-model="producto.precio">
            <br> <br>
          </div>
          <div class="modal-footer">
            <p id="exito">Agregado con exito</p>
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cerrar</button>
            <button @click="agregar(producto.codigo)" type="button" class="btn btn-primary" data-bs-dismiss="modal">Guardar cambios</button>
          </div>
        </div>
      </div>
    </div>

    <!-- <div id="form">
      <p>Código: </p><input type="text" v-model="producto.codigo">
      <p>Producto: </p><input type="text" v-model="producto.nombre">
      <p>Costo: </p><input type="number" v-model="producto.costo">
      <p>Cantidad: </p><input type="number" v-model="producto.cantidad">
      <p>Precio: </p><input type="number" v-model="producto.precio">
      <br> <br>
      <button @click="agregar()">Enviar</button>

    </div> -->

    <table>
      <tr>
        <td>Codigo</td>
        <td>Nombre</td>
        <td>Costo</td>
        <td>Cantidad</td>
        <td>Precio</td>
        <td>Opciones</td>
      </tr>

      <tr v-for="(item, index) in data" :key="index">
        <td>{{ item.codigo }}</td>
        <td>{{ item.nombre }}</td>
        <td>{{ item.costo }}</td>
        <td :style="getColor(item.cantidad)">{{ item.cantidad }}</td>
        <td>{{ item.precio }}</td>
        <td>
          <button @click="editar(item)" data-bs-toggle="modal" data-bs-target="#exampleModal">✍️</button>
          <button @click="eliminar(index)">❌</button>
        </td>
      </tr>

    </table>
  </div>
</template>

<style scoped>
#form {
  /* display: grid;
  grid-template-columns: 15% 85%; */
  width: 400px;
}

table {
  margin: 10px;
  border: 1px solid black;
}

td {
  border: 1px solid black;
}
</style>
