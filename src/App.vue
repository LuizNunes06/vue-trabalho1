<script setup>
import { ref } from 'vue'

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
const msgErro = ref('')

function confirma() {
  if (senha.value == senha2.value) {
    msgErro.value = "";
  return true;
  }
  else {
    msgErro.value = "senha e nova senha não conferem."
    return false;
  }
}


</script>

<template>
  <div class="geral">
  <form @submit.prevent="confirmaUsuario=confirma()" class="formulario">
    <div class="menu">
      <p>Nome: </p><input v-model="nome" placeholder="Nome" minlength="3" maxlength="20" required />
    <p>Email: </p><input type="email" v-model="email" placeholder="Email" required />
    <p>Senha: </p><input type="password" v-model="senha" required />
    <p>Confirmação de senha: </p><input type="password" v-model="senha2" required />
    <p>Nascimento: </p><input type="date" name="Data nascimento" id="nascimento" v-model="nascimento">
    <p>Endereço: </p><input type="text" v-model="endereco" required />
    <p>Cidade: </p><input type="text" v-model="cidade" required />
    
    <p>Estado: </p><select v-model="estados">
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
    <p>Hobbies: </p><textarea v-model="hobbies" cols="20" rows="5"></textarea>
    <p>Linguagens de programação: </p><textarea v-model="lingProg" cols="20" rows="5"></textarea>
    <p>Biografia: </p><textarea v-model="bio" cols="20" rows="5"></textarea>
    <button type="submit" class="botao">Enviar</button>
    <p>{{ msgErro }}</p>
  </div>
</form> 

<div v-if="confirmaUsuario" class="formulario2">
  
  <div class="respostas">
    <p>Usuario Criado</p>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
    <p>Data de nascimento: {{ nascimento }}</p>
    <p>Endereço: {{ endereco }}</p>
    <p>Cidade: {{ cidade }}</p>
    <p>Estado: {{ estados }}</p>
    <p>Hobbies: {{ hobbies }}</p>
    <p>Linguagens de programação: {{ lingProg }}</p>
    <p>Biografia: {{ bio }}</p>
  </div>
  
</div>

</div>
</template>

<style scoped>

.formulario{
  color: aliceblue;
    background-color: #0E4459;
    width: 400px;
    border-radius: 10px;
    margin-left: 20%;
  }
  .formulario2{
  color: aliceblue;
    background-color: #0E4459;
    width: 400px;
    height: 800px;
    border-radius: 10px;
    margin-left: 20%;
  }
  .menu{
    margin: 60px 60px 60px 100px;
    padding-top: 20px;
  }
  .botao{
    font-size: 15px;
    color: aliceblue;
    background-color: #0C4B59;
    border: solid 1px #95BFB8;
    border-radius: 10px;
    height: 40px;
    width: 205px;
    margin: 30px 20px 20px 0px
  }
  textarea{
    background-color: whitesmoke;
    border: none;
    width: 200px;
  }
  input, select{
    background-color: whitesmoke;
    border: none;
    height: 20px;
    width: 200px;
  }
  .respostas{
    color: aliceblue;
    background-color: #0E4459;
    margin: 10px 60px 60px 100px;
    padding: 20px;
  }
  .geral{
    display: grid;
    grid-template-columns: 50% 50%;
  }

</style>
