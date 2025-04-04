<script setup>
import { ref } from 'vue'

const contador1 = ref (0);
const contador2 = ref(0);

function incrementar1 () {
  contador1.value++
}

function decrementar1 () {
  contador1.value--
}
function incrementar2 () {
  contador2.value++
}

function decrementar2 () {
  contador2.value--
}
</script>

<template>
  <div>
    <h1>Contador 1</h1>
    <p>Valor do contador : {{ contador1 }}</p>

    <button @click="incrementar1">+</button>
    <button @click="decrementar1">-</button>
  </div>
  <div>
    <h1>Contador 2</h1>
    <p>Valor do contador : {{ contador2 }}</p>

    <button @click="incrementar2">+</button>
    <button @click="decrementar2">-</button>
  </div>
  <div>
    <p>A soma dos contadores é: {{ contador1 + contador2 }}</p>
  </div>
</template>

<style scoped>
 button{
  background-color: aqua;
  margin: 2vw;
  color: black;
  padding: 15px;
  border-radius: 10px;
 }
 div p {

 }
</style>
