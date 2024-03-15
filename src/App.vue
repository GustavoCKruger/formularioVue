<script setup>
import { computed, ref } from 'vue';

const nome = ref('');
const idade = ref('');
const email = ref('');

function enviar() {
  if (nome.value <= 3) {
    alert("a");
  }
}
</script>

<template>
  <div class="form">
    <div class="nome">
      <p>Nome:</p>
      <input type="text" v-model="nome" minlength="3" maxlength="20" placeholder="Digite seu nome">
    </div>
    <p>Idade:</p>
    <div class="idade">
      <input type="number" v-model="idade">
    </div>
    <div class="email">
      <p>Email:</p>
      <input type="email" v-model="email" placeholder="Digite um email válido">
    </div>
    <div class="enviar">
      <input type="button" value="Enviar" @click="enviar()">
    </div>
  </div>
</template>

<style scoped></style>