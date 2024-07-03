<script setup>
import { ref } from "vue";

const perfil = ref({
  nome: '',
  email: '',
  senha: '',
  nascimento: '',
  endereco: '',
  estado: '',
  linguagem: '',
  biografia: '',
  hobbies: '',
  cidade: '',
})
const confrimarsenha = ref("")
const listaEstados = ref([
  { 'nome': 'Acre', 'sigla': 'AC-' },
  { 'nome': 'Alagoas', 'sigla': 'AL-' },
  { 'nome': 'Amapá', 'sigla': 'AP-' },
  { 'nome': 'Amazonas', 'sigla': 'AM-' },
  { 'nome': 'Bahia', 'sigla': 'BA-' },
  { 'nome': 'Ceará', 'sigla': 'CE-' },
  { 'nome': 'Distrito Federal', 'sigla': 'DF-' },
  { 'nome': 'Espírito Santo', 'sigla': 'ES-' },
  { 'nome': 'Goiás', 'sigla': 'GO-' },
  { 'nome': 'Maranhão', 'sigla': 'MA-' },
  { 'nome': 'Mato Grosso', 'sigla': 'MT-' },
  { 'nome': 'Mato Grosso do Sul', 'sigla': 'MS-' },
  { 'nome': 'Minas Gerais', 'sigla': 'MG-' },
  { 'nome': 'Pará', 'sigla': 'PA-' },
  { 'nome': 'Paraíba', 'sigla': 'PB-' },
  { 'nome': 'Paraná', 'sigla': 'PR-' },
  { 'nome': 'Pernambuco', 'sigla': 'PE-' },
  { 'nome': 'Piauí', 'sigla': 'PI-' },
  { 'nome': 'Rio de Janeiro', 'sigla': 'RJ-' },
  { 'nome': 'Rio Grande do Norte', 'sigla': 'RN-' },
  { 'nome': 'Rio Grande do Sul', 'sigla': 'RS-' },
  { 'nome': 'Rondônia', 'sigla': 'RO-' },
  { 'nome': 'Roraima', 'sigla': 'RR-' },
  { 'nome': 'Santa Catarina', 'sigla': 'SC-' },
  { 'nome': 'São Paulo', 'sigla': 'SP-' },
  { 'nome': 'Sergipe', 'sigla': 'SE-' },
  { 'nome': 'Tocantins', 'sigla': 'TO-' },
])
const mostrarresultado = ref(false)


</script>


<template>
  <main>
  <div class="tudo">
      <div v-if ="!mostrarresultado" class="formulario">
        <div class="tittle">
          <h1>Registro de Usuario</h1>
        </div>
        <div class="usuario-informações">
          <label for="perfil.nome">Informe seu nome:</label>
          <div class="usuario-nome above-inputs">
            <input v-model="perfil.nome" type="text" min="3" max="20" required>
          </div>
          <label for="perfil.email">Informe seu e-mail:</label>
          <div class="usuario-email above-inputs">
            <input v-model="perfil.email" type="email" required>
          </div>
          <label for="perfil.senha">Informe sua senha:</label>
          <div class="usuario-senha above-inputs">
            <input v-model="perfil.senha" type="password" required>
          </div>
          <label for="confirmarsenha">Confirme sua senha:</label>
          <div class="usuario-verify-senha above-inputs">
            <input v-model="confrimarsenha" type="password" required>
            <p v-if="perfil.senha !== confrimarsenha">Incorreto!</p>
          </div>
          <label for="perfil.nascimento">Informe sua data de nascimento:</label>
          <div class="usuario-nascimento above-inputs">
            <input v-model="perfil.nascimento" type="date" required>
          </div>
          <label for="perfil.endereco">Informe seu Endereço:</label>
          <div class="usuario-endereco above-inputs">
            <input class="buttons-f1" v-model="perfil.endereco"  required>
          </div>
          <label for="perfil.cidade">Informe sua Cidade:</label>
          <div class="usuario-city above-inputs">
            <input v-model="perfil.cidade" type="text" required>
          </div>
          <label for="perfil.hobbies">Qual seu Hobbie:</label>
          <div class="usuario-hobbies above-inputs">
          <input v-model="perfil.hobbies" type="text" required>
          </div>

          <label for="perfil.linguagem">Qual sua linguagem de programação:</label>
          <div class="usuario-linguagem above-inputs">
          <input v-model="perfil.linguagem" type="text" required>
          </div>

          <label for="perfil.estado">Informe seu Estado</label>
          <div class="usuario-estados">
            <select v-model="perfil.estado">
              <option v-for="(value, index) of listaEstados" :key="index">{{ value.sigla
                }}{{ value.nome }}</option>
            </select>
          </div>
          <label for="perfil.biografia">Escreva sua Biografia</label>
          <div class="biografia-graphy">
            <textarea v-model="perfil.biografia" nome="biografia" cols="40" rows="5" required>biografia</textarea>
          </div>
          <button class="btn btn-white" @click="mostrarresultado= !mostrarresultado" >Enter</button>
        </div>
    </div>
    <section>
      <div v-if="mostrarresultado" class="resultado">
        <h2>Dados do Usuario</h2>
        <p>Nome : {{ perfil.nome }}</p>
        <p>email : {{ perfil.email }}</p>
        <p>nascimento : {{ perfil.nascimento }}</p>
        <p>endereço : {{ perfil.endereco }}</p>
        <p>Estado : {{ perfil.estado }}</p>
        <p>Linguagem : {{ perfil.linguagem }}</p>
        <p>biografia : {{ perfil.biografia }}</p>
        <p>Hobbies : {{ perfil.hobbies }}</p>
        <p>Cidade : {{ perfil.cidade }}</p>
        <button class="btn btn-white" @click="mostrarresultado= !mostrarresultado" >Voltar</button>
      </div>
    </section>
  </div>
  </main>
</template>


<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

input{
  border: color(white);
  color: rgb(248, 248, 248);
}
main {
  position: relative;
  align-items: center;
  display: flex;
  justify-content: center;
}

.formulario {
  backdrop-filter: formulario(5px);
}

.btn {
  background-color: rgb(68, 55, 55);
  color: white;
  align-items: center;
}

.active {
  border: solid 10px black;
}

.formulario{
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
  color: white;
  border: color(white);
  background-color: rgb(68, 65, 65);
}

.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
  background-color: rgb(68, 65, 65);
  color: white;
}

.usuario-informações input,
usuario-estados select {
  border-radius: 5px;
  border: 2px solid rgb(5, 43, 25);
  background-color: rgba(26, 78, 22, 0);
}

.usuario-informações {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.above-inputs {
  margin: 5px 0px 8px 0px;
}

.tittle {
  display: flex;
  justify-content: center;  
  align-items: center;
  background-color: rgb(68, 65, 65);
  color: white;
}

::placeholder{
  color: white;
}

label{
  padding-top: 10px;
}

</style>
