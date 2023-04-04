<script setup>
import { ref, computed } from 'vue'

const nome = ref('');
const email = ref('');
const senha = ref('');
const senha2 = ref('')
const confirmaUsuario = ref(false);

// eslint-disable-next-line vue/return-in-computed-property
const confirma = computed(() => {
  if (email.value.includes("@") && nome.value.length > 3 && nome.value.length <= 20 && senha.value == senha2.value) {
   // eslint-disable-next-line vue/no-side-effects-in-computed-properties
  confirmaUsuario.value = true;

  }
})


</script>

<template>
  <form @submit.prevent="">
    <input v-model="nome" placeholder="Nome" minlength="3" maxlength="20" required />
    <input type="email" v-model="email" placeholder="Email" required />
    <input type="password" v-model="senha" required />
    <input type="password" v-model="senha2" required />
    <button type="submit" @click="confirma" >Enviar</button>

    <div v-if=" confirmaUsuario == true">
      <p>Usuario Criado</p>
      <p>Nome: {{ nome }}</p>
      <p>email: {{ email }}</p>
      <p>idade: {{ senha }}</p>
    </div>
  </form>
</template>

<style scoped></style>
