<script setup>
import { ref } from 'vue';

let modules = ref('')

let turno1 = ref (['pppppp'])
let turno2 = ref (['aaaaaa'])
let turno3 = ref (['xxxxxx']) 
 
let ubica = ref()

function pusheo(){

  if(ubica.value == 'modulo1'){
    turno1.value.push(modules.value)
  }
  if(ubica.value == 'modulo2'){
    turno2.value.push(modules.value)
  }
  if(ubica.value == 'modulo3'){
    turno3.value.push(modules.value)
  }
 
}


</script>

<template>
<div class="justify-between max-w-2xl m-auto bg-slate-400 rounded-xl">
  <div class="p-2">
    Modulos
  </div>
  <div class="flex justify-between p-5 text-center">
    <div>
      <button class="bg-orange-400 rounded h-12 w-24">Modulo 1</button> 
      <div class="mt-5" v-for="(i,index) in turno1 " :key="index">
        {{ i }}
    </div>
    </div>
    <div>
      <button class="bg-green-400 rounded h-12 w-24">Modulo 2</button> 
      <div class="mt-5" v-for="(i,index) in turno2 " :key="index">
     {{ i }}
    </div>
    </div>
    <div>
      <button class="bg-blue-400 rounded h-12 w-24">Modulo 3</button>
      <div class="mt-5" v-for="(i,index) in turno3 " :key="index">
      {{ i }}
      </div>
    </div>
  </div>
  <div class="flex justify-between p-5 text-center">
    <p>turnos</p>
    <select name="hola" id="" v-model="ubica">
      <option value="modulo1">modulo 1</option>
      <option value="modulo2">modulo 2</option>
      <option value="modulo3">modulo 3</option>
    </select>
    <input v-model="modules" type="text" placeholder="codigo">

    <button @click="pusheo" class="bg-purple-600 rounded h-12 w-24>Agregar turno">Agregar turno</button>
  </div>
</div>
</template>

<style scoped>

</style>
