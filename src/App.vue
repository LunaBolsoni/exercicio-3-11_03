<script setup>
import { ref } from 'vue';
const listaC = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília',
])

const novoItem = ref('')

function adicionarItem() {
  listaC.value.push(novoItem.value)
  novoItem.value = ''
}

function remover(i) {
  listaC.value.splice(i, 1)
}

</script>

<template>
  <div>
    <h1>Cidades:</h1>
    <ul>
      <li v-for="cidades in listaC" :key="cidades">{{ cidades }} <button @click="remover(i)">Remover </button></li>
       
    </ul>
  </div>

  <input type="text" v-model="novoItem">
  <button @click="adicionarItem"> Aicionar</button>
  <ul>
    <li v-for="item in ListaC">{{ item }} </li>
  </ul>

</template>


<style scoped></style>
