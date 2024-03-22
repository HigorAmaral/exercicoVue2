<script setup>
import { ref } from 'vue'

const name = ref(``);
const email = ref(``);
const senha = ref(``);
const confirmaSenha = ref(``); 
const nascimento = ref(``);
const endereco = ref(``);
const cidade = ref(``);
const estado = ref(``);
const hobbies = ref(``);
const linguagens = ref(``);
const biografia = ref(``);

</script>

<template>
  <div class="form">
    <h1>Formulário</h1>
    <label for="nome">Informe seu nome</label>
    <input type="text" name="nome" id="nome" placeholder="Nome" required />

    <label for="email">Informe o seu email</label>
    <input type="email" v-model="email" placeholder="Email" required />

    <label for="senha">Informe a sua senha</label>
    <input type="password" v-model="senha" placeholder="Senha" required />

    <label for="confirme a senha">Confirme a sua senha</label>
    <input type="password" v-model="confirmaSenha" placeholder="Confirme a senha" required />

    <label for="nascimento">Data de Nascimento</label>
    <input type="date" v-model="nascimento" placeholder="Data de nascimento" required />

    <label for="endereco">Informe o seu Endereço</label>
    <input type="text" v-model="endereco" placeholder="Endereço" required />

    <label for="cidade">Informe a sua cidade</label>
    <input type="text" v-model="cidade" placeholder="Cidade" required />

    <label for="estado">Informe o seu Estado</label>
    <select id="estado" name="estado">
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goiás</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>

    <label for="hobbies">Informe o seu Hobbies</label>
    <input type="text" v-model="hobbies" placeholder="Hobbies" />

    <label for="suas Linguagens De Prog...">Informe a sua línguagen de programação</label>
    <input type="text" v-model="linguagens" placeholder="Suas Linguagens De Prog..." />

    <label for="biografia">Faça sua Biografia</label>
    <textarea name="biografia" id="biografia" cols="30" rows="20" maxlength="5000"></textarea>

    <button id="botaoEnviar">Enviar</button>
  </div>

  <div class="informacoes">
    <h1>informacoes do Usuário</h1>
  </div>
</template>

<style>
.form {
  display: flex;
  flex-direction: column;
  background-color: rgb(235, 230, 171);
  height: 50%;
  width: 50%;
  align-items: center;
  margin: 0 auto;
}

button {
  background-color: rgb(52, 52, 255);
  margin-top: 20px;
}

input {
  margin-top: 5px;
  margin-bottom: 5px;
  height: 80%;
  width: 80%;
  border-radius: 15px;
}

select {
  height: 80%;
  width: 80%;
  border-radius: 15px;
}

textarea {
  height: 80%;
  width: 80%;
  border-radius: 15px;
}
</style>
