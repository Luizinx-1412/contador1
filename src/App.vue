<script setup>
import { ref } from 'vue'

const contador1 = ref(0);
const contador2 = ref(0);
const booleano = ref(true);

function incrementar1() {
  contador1.value++
}

function decrementar1() {
  contador1.value--
}
function incrementar2() {
  contador2.value++
}

function decrementar2() {
  contador2.value--
}
function ehPar(num) {
  return num % 2 == 0;
}
function maiorQ10 (numero) {
  return numero > 10;
}
</script>

<template>
  <div class="esconder">
    <button @click="booleano = !booleano" >
      {{ booleano ? "Esconder conteúdo " : "Mostrar conteúdo" }}
    </button>
  </div>
  <div v-if="booleano">
  <div class="contadores">
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
  </div>
  <div>
    <p>A soma dos contadores é: {{ contador1 + contador2 }}</p>
  </div>
  <div v-if="ehPar(contador1 + contador2) == true">
    <p>A soma é par</p>
  </div>
  <div v-else>
    <p>A soma é impar</p>
  </div>
  <div v-if = "maiorQ10(contador1 + contador2) == true">
   <p><span class="maior">O valor é maior que 10</span></p>
  </div>
  <div v-else-if="contador1 + contador2 === 10">
   <p><span class="igual">O valor é igual a 10</span></p>
  </div>
  <div v-else>
    <p><span class="menor">O valor é menor que 10</span></p>
  </div>
</div>
</template>

<style scoped>
button {
  cursor: pointer;
  color: rgb(112, 17, 121);
  background-color: rgb(0, 19, 126);
  margin: 2vw;
  padding: 15px;
  border-radius: 10px;
  border-color: rgb(112, 17, 121);
  /* border: 0 */
}
h1{
  color: rgb(234, 0, 255);
}
p{
  color: blue;
}
div.contadores{
 display: flex;
}
.maior{
  color: green;
}
.igual{
  color: yellow;
}
.menor{
  color: brown;
}
/* div p {} */
</style>
