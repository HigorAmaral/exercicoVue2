<script setup>
import { ref } from 'vue'
</script>

<template>
  <div class="form">
    <h1>Formulário</h1>
    <input type="text" v-model="nome" placeholder="Nome" required />

    <input type="email" v-model="email" placeholder="Email" required />

    <input type="password" v-model="senha" placeholder="Senha" required />

    <input type="password" v-model="confirmaSenha" placeholder="Confirme a senha" required />

    <label for="nascimento">Data de Nascimento</label>
    <input type="date" v-model="nascimento" placeholder="Data de nascimento" required />

    <input type="text" v-model="endereco" placeholder="Endereço" required />

    <input type="text" v-model="cidade" placeholder="Cidade" required />

    <input type="text" v-model="estado" placeholder="Estado" />

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

    <input type="text" v-model="hobbies" placeholder="Hobbies" />

    <input type="text" v-model="linguagens" placeholder="Suas Linguagens De Prog..." />

    <label for="Biografia">Faça sua Biografia</label>
    <textarea name="biografia" id="biografia" cols="30" rows="20" maxlength="5000"></textarea>
  </div>
</template>

<style>
.form {
  display: flex;
  flex-direction: column;
  background-color: rgb(235, 230, 171);
  height: 40%;
  width: 40%;
  align-items: center;
  margin: 0 auto;
}

input {
  margin-top: 5px;
  margin-bottom: 5px;
  height: 80%;
  width: 80%;
}

select {
  height: 80%;
  width: 80%;
}

textarea {
  height: 80%;
  width: 80%;
}
</style>
