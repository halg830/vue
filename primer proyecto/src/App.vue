<template>
  <div>
    <!-- <h1 :style="colores">{{ num }}</h1>
      <h1 v-text="num"></h1>
      <h1 v-html="codigo"></h1>
      <h1 v-pre>{{ codigo }}</h1>
      <h1 v-once>Este solo actuliza una vez el valor {{ num }}</h1>
     v-model obtiene el value de input 
      <input type="text" placeholder="nombre" v-model="caja">
      <button v-on:click="prueba()">click</button> -->

    <!-- 2cajas 2 numero y que muestre el resultado -->
    <!-- <input type="number" v-model="caja1">
      <br>
      <br>
      <input type="number" v-model="caja2">
      <h1>Resultado: {{parseInt(caja1)+parseInt(caja2) }}</h1>

      <select v-model="listItems">
      <option value="A">opcion a</option>
      <option value="B">opcion b</option>
      <option value="C">opcion c</option>
      </select> -->

    <!-- <label for=""><input type="radio" name="prueba" v-model="radio" value="A">A</label>
      <br>
      <label for=""><input type="radio" name="prueba" v-model="radio" value="B">B</label>
      <br>
      <label for=""><input type="radio" name="prueba" v-model="radio" value="C">C</label>
      <br>

      <h1>{{ radio }}</h1> -->

    <!-- <label for=""><input type="checkbox" name="check" value="A" v-model="check">A</label>
      <label for=""><input type="checkbox" name="check" value="B" v-model="check">B</label>
      <label for=""><input type="checkbox" name="check" value="C" v-model="check">C</label>
        
      <h1>{{ check }}</h1> -->

    <!-- <div v-show="edad>=18">
        <h1>hola</h1>
      </div> -->

    <!--  <div v-if="edad>=18">
        <h1>hola</h1>
      </div>
      <div v-else>
<h1>adios</h1>
      </div> -->

    <!-- <label for=""><input type="radio" name="prueba" v-model="framework" value="react">React</label>
    <br>
    <label for=""><input type="radio" name="prueba" v-model="framework" value="angular">Angular</label>
    <br>
    <label for=""><input type="radio" name="prueba" v-model="framework" value="vue">Vue</label>
    <br>

    <div v-if="framework==='react'"><img src="data:image/png;base64,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" alt=""></div>
    <div v-else-if="framework==='angular'"><img src="data:image/png;base64,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" alt=""></div>
    <div v-else-if="framework==='vue'"><img src="data:image/png;base64,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" alt=""></div>
 -->

 <!-- <div>
  <ul>
    <li v-for="(item, i) in frutas" :key="i"> {{ item }} <button>✍️</button></li>
  </ul>
 </div>-->

 <!-- <img :src="imagen" alt=""> -->

<!-- <ul>
  <li v-for="(item, i) in numbers" :key="i" :style="item<18?'color:red':'color:green'">{{ item }}</li>
</ul> -->

<!-- 5 cajas = codigo, nombreproducto, precio a como se vende, cantidad, costo a como me lo venden 
button agregar añadir a un vector 
pintar en una tabla el vector
if la cantidad de un producto es menor a 10 unidades coloca de rojo
else if mayor a 50 unidades azul
else negro
-->

<input type="text">
<input type="text">
<input type="text">
<input type="text">

<table>
  <tr>
    <td>Codigo</td>
    <td>Nombre</td>
    <td>Precio</td>
    <td>Cantidad</td>
    <td>Cargo</td>
  </tr>
</table>

  </div>
</template>

<script setup>
import { ref } from 'vue'

// const numbers = ref([14, 23, 31, 15 ,1, 34, 32, 56, 2, 45, 23])


// let imagen = ref("data:image/png;base64,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")

/* let frutas = ref(["manzana", "pera", "banano"]) */
 
/* let framework = ref() */

/* let edad = ref("18") */

/* let radio = ref()
let check = ref([]) */

/* let listItems = ref("C")

let caja1 = ref(5)
let caja2 = ref(5) */

/* const arr = [0, 1, 2]

let codigo = ref("<p>hola</p>")
let caja = ref("soy una caja")

let num = ref(0)
let colores = ref("color: white;")
const prueba = ()=>{
  num.value +=1
  colores.value = "color: red;"
} */


</script>

<style scoped>
h1 {
  color: white;
}
table{
  border: 1px solid white;
}
</style>
