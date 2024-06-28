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
      <div v-if ="!mostrarresultado" class="formulario">
        <div class="tittle">
          <h1>Registro de Usuario</h1>
        </div>
        <div class="usuario-informações">
          <div class="usuario-nome above-inputs">
            <input v-model="perfil.nome" placeholder="Informe seu nome" type="text" required>
          </div>
          <div class="usuario-email above-inputs">
            <input v-model="perfil.email" placeholder="Informe seu email" type="email" required>
          </div>
          <div class="usuario-senha above-inputs">
            <input v-model="perfil.senha" placeholder="Informe sua senha" type="senha" required>
          </div>
          <div class="usuario-verify-senha above-inputs">
            <input v-model="confrimarsenha" placeholder="Confirme a sua senha" type="senha" required>
            <p v-if="perfil.senha !== confrimarsenha">Incorreto!</p>
          </div>
          <div class="usuario-nascimento above-inputs">
            <input v-model="perfil.nascimento" placeholder="Qual é sua data de nascimento" type="date" required>
          </div>

          <div class="usuario-endereco above-inputs">
            <input class="buttons-f1" v-model="perfil.endereco" placeholder="Qual o seu endereço?" required>
          </div>

          <div class="usuario-city above-inputs">
            <input v-model="perfil.cidade" placeholder="Qual sua cidade?" type="text" required>
          </div>
          <div class="usuario-liguagem above-inputs">
            <input v-model="perfil.linguagem" placeholder="Qual sua liguagem de programação?" type="text" required>
          </div>
          <div class="usuario-hobbies">
            <input v-model="perfil.hobbies" placeholder="Qual seu hobbie?" type="text" required>
          </div>
          <div class="usuario-estados">
            <select v-model="perfil.estado">
              <option v-for="(value, index) of listaEstados" :key="index">{{ value.sigla
                }}{{ value.nome }}</option>
            </select>
          </div>
          <div class="biografia-graphy">
            <textarea v-model="perfil.biografia" nome="biografia" cols="40" rows="8" required>biografia</textarea>
          </div>
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
        <p>email : {{ perfil.email }}</p>
      </div>
    </section>
    <button class="btn btn-white" @click="mostrarresultado= !mostrarresultado" >Perfil</button>
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
  background-color: rgb(22, 12, 12);
  color: white;
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
  background-color: rgb(0, 0, 0);
}

.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
  background-color: black;
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
  background-color: black;
  color: white;
}

::placeholder{
  color: white;
}

</style>
