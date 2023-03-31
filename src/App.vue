<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const idade = ref()
const confirmaUsuario = ref(false)

</script>

<template>
  <form>
  <input v-model="nome" placeholder="Nome"  minlength="3" maxlength="20" required/>
  <input type="email" v-model="email" placeholder="Email" required/>
  <input type="number" v-model="idade" required/>
  <button type="submit" @click="confirmaUsuario = true">Enviar</button>
</form>
  <div v-if="confirmaUsuario == true">
      <p>Usuario Criado</p>
      <p>Nome: {{ nome }}</p>
      <p>email: {{ email }}</p>
      <p>idade: {{ idade }}</p>
  </div>
  
</template>

<style scoped></style>
