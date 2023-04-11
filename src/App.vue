<script setup>
import { ref, computed } from 'vue'

const nome = ref('');
const email = ref('');
const senha = ref('');
const senha2 = ref('')
const confirmaUsuario = ref(false);
const nascimento = ref('');
const endereco = ref('');
const estados = ref('');
const hobbies = ref('');
const lingProg = ref('');
const bio = ref('');


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
    <div>
    <input v-model="nome" placeholder="Nome" minlength="3" maxlength="20" required />
    <input type="email" v-model="email" placeholder="Email" required />
    <input type="password" v-model="senha" required />
    <input type="password" v-model="senha2" required />
    <input type="date" name="Data nascimento" id="nascimento" v-model="nascimento">
    <input type="text" v-model="endereco" required />
    <input type="text" v-model="cidade" required />

    <select v-model="estados">
      <option value=" Acre">AC</option>
      <option value="Alagoas">AL</option>
      <option value="Amapá">AP</option>
      <option value="Amazonas">AM</option>
      <option value="Bahia">BA</option>
      <option value="Ceará">CE</option>
      <option value="Distrito Federal">DF</option>
      <option value="Espírito Santo">ES</option>
      <option value="Goiás">GO</option>
      <option value="Maranhão">MA</option>
      <option value="Mato Grosso">MT</option>
      <option value="Mato Grosso do Sul">MS</option>
      <option value="Minas Gerais">MG</option>
      <option value="Pará">PA</option>
      <option value="Paraíba">PB</option>
      <option value="Paraná">PR</option>
      <option value="Pernambuco">PE</option>
      <option value="Piauí">PI</option>
      <option value="Rio de Janeiro">RJ</option>
      <option value="Rio Grande do Norte">RN</option>
      <option value="Rio Grande do Sul">RS</option>
      <option value="Rondônia">RO</option>
      <option value="Roraima">RR</option>
      <option value="Santa Catarina">SC</option>
      <option value="São Paulo">SP</option>
      <option value="Sergipe">SE</option>
      <option value="Tocantins">TO</option>
    </select>
    <textarea v-model="hobbies" cols="30" rows="10"></textarea>
    <textarea v-model="lingProg" cols="30" rows="10"></textarea>
    <textarea v-model="bio" cols="30" rows="10"></textarea>
    <button type="submit" @click="confirma" >Enviar</button>
  </div>
</form> 

<div v-if=" confirmaUsuario == true">
      <p>Usuario Criado</p>
      <p>Nome: {{ nome }}</p>
      <p>Email: {{ email }}</p>
      <p>Senha: {{ senha }}</p>
      <p>Data de nascimento: {{ nascimento }}</p>
      <p>Endereço: {{ endereco }}</p>
      <p>Cidade: {{ cidade }}</p>
      <p>Estado: {{ estados }}</p>
</div>

</template>

<style scoped></style>
