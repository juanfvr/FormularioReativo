<script setup>
import {ref} from "vue";

const nome = defineModel('nome');
const sobrenome = defineModel('sobrenome');
const username = defineModel('username');
const idade = defineModel('idade');
const email = defineModel('email');
const senha = defineModel('senha');

let inputColor = ref('');
let textColor = ref('');

function isFieldNull(field) {
  if(field) {
    inputColor.value = 'border: 2px solid var(--primary-color)';
    textColor.value = 'color: var(--primary-color)';
  } else {
    inputColor.value = 'border: 2px solid red';
    textColor.value = 'color: red';
  }
}

function submit(e) {
  if(nome.value === undefined || sobrenome.value === undefined || username.value === undefined || idade.value === undefined || email.value === '' || senha.value === undefined) {
    e.preventDefault();
    console.log('a');
  }
}

</script>

<template>
  <div class="form-container">
    <form action="">
      <section class="full-name">
        <div class="form-input">
        <label for="nome" :style="isFieldNull(nome)">Nome</label>
          <input
              type="text"
              autocomplete="false"
              v-model="nome"
              :style="inputColor"
              >
          <span v-if="!nome" :style="textColor">Campo em branco</span>
        </div>
        <div class="form-input">
          <label for="nome" :style="isFieldNull(sobrenome)">Sobrenome</label>
          <input
              type="text"
              autocomplete="false"
              v-model="sobrenome"
              :style="inputColor"
          >
          <span v-if="!sobrenome" :style="textColor">Campo em branco</span>
        </div>
      </section>
      <section class="username-age">
        <div class="form-input">
          <label for="nome" :style="isFieldNull(username)">Nome de usuário</label>
          <input
              type="text"
              autocomplete="false"
              v-model="username"
              :style="inputColor"
          >
          <span v-if="!username" :style="textColor">Campo em branco</span>
        </div>
        <div class="form-input">
          <label for="nome" :style="isFieldNull(idade)">Idade</label>
          <input
              type="number"
              autocomplete="false"
              min="12"
              max="100"
              v-model="idade"
              :style="inputColor"
          >
          <span v-if="!idade" :style="textColor">Campo em branco</span>
        </div>
      </section>
      <section class="email-password">
          <div class="form-input">
            <label for="nome" :style="isFieldNull(email)">E-mail</label>
            <input
                type="text"
                autocomplete="false"
                v-model="email"
                :style="inputColor"
            >
            <span v-if="!email" :style="textColor">Campo em branco</span>
          </div>
          <div class="form-input">
            <label for="nome" :style="isFieldNull(senha)">Senha</label>
            <input
                type="text"
                autocomplete="false"
                v-model="senha"
                :style="inputColor"
            >
            <span v-if="!senha" :style="textColor">Campo em branco</span>
          </div>
      </section>
      <button class="btn-submit" @click="submit">Finalizar</button>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  background: white;
  min-width: fit-content;
  padding: 20px;
  border-radius: 8px;
}

form {
  width: fit-content;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.full-name {
  display: flex;
  gap: .5em;

  @media (max-width: 425px) {
    flex-wrap: wrap;
}
}

.username-age {
  display: flex;
  gap: .5em;

  @media (max-width: 425px) {
    flex-wrap: wrap;
}
}

.email-password {
  display: flex;
  flex-direction: column;
  gap: 8px;

  @media (max-width: 425px) {
    flex-wrap: wrap;
}
}

.form-input {
  display: flex;
  flex-direction: column;
  width: 100%;
  color: var(--primary-color);
}

input {
  border: 2px solid var(--primary-color);
  padding: .4em;
  border-radius: 8px;
  outline: none;
}

.btn-submit {
  width: 100%;
  padding: 12px;
  border: none;
  border-radius: 8px;
  background: var(--btn-color);
  color: white;
  font-weight: bold;
  font-size: 1em;
}

span {
  font-size: .8em;
}
</style>