<script setup>

import { ref } from 'vue';

const usuario = ref({
  nome: '',
  idade: '',
  email: ''
});

function enviar() {
  alert(`Seus dados são: \nNome: ${usuario.value.nome} \nIdade: ${usuario.value.idade} \nEmail: ${usuario.value.email}`)

  if (usuario.value.idade < 18) {
    alert(`Apenas maiores de idade 🚫18`);
  }
  else if (usuario.value.idade > 60) {
    alert(`Apenas menores da era paleozoica`);
  }
}

</script>

<template>
  <form>
    <div class="nome">
      <label for="nome">Nome:</label>
      <br>
      <input class="placeholder" minlength="3" maxlength="20" type="text" name="nome" id="nome" v-model="usuario.nome"
        placeholder=" Insira seu nome aqui">
    </div>

    <div class="idade">
      <label for="idade">Idade:</label>
      <br>
      <input class="placeholder" type="number" name="idade" id="idade" v-model="usuario.idade"
        placeholder=" Insira sua idade aqui">
    </div>

    <div class="email">
      <label for="email">Email:</label>
      <br>
      <input class="placeholder" type="email" name="email" id="email" v-model="usuario.email"
        placeholder=" Insira seu email aqui">
    </div>
    <br>
    <button type="submit" @click="enviar()">Enviar</button>
  </form>
</template>

<style scoped>
form {
  background-color: burlywood;
  max-height: 100vh;
  max-width: 100vh;
  border: 20px black;
}

.placeholder {
  width: 30vh;
}
</style>