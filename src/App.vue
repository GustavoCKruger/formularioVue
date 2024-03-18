<script setup>

import { ref } from 'vue';

const usuario = ref({
  nome: '',
  idade: '',
  email: ''
});

function enviar() {
  alert(`Seus dados são: \nNome: ${usuario.value.nome} \nIdade: ${usuario.value.idade} \nEmail: ${usuario.value.email}`)

  if (usuario.value.idade < 18 || usuario.value.idade > 60) {
    alert(`Arrume sua idade`)
  }
}

</script>

<template>
  <form>
    <div class="nome">
      <label for="nome">Nome:</label>
      <input type="text" name="nome" id="nome" v-model="usuario.nome" placeholder="Insira seu nome aqui">
    </div>

    <div class="idade">
      <label for="idade">Idade:</label>
      <input type="number" name="idade" id="idade" v-model="usuario.idade">
    </div>

    <div class="email">
      <label for="email">Email:</label>
      <input type="email" name="email" id="email" v-model="usuario.email" placeholder="Insira seu email aqui">
    </div>

    <button type="submit" @click="enviar()">Enviar</button>
  </form>
</template>

<style scoped></style>