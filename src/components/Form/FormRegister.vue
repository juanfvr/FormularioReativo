<script setup>
import Input from "@/components/Form/Input.vue";
import Button from "@/components/Form/Button.vue";

const nome = defineModel('nome');
const sobrenome = defineModel('sobrenome');
const username = defineModel('username');
const idade = defineModel('idade');
const email = defineModel('email');
const senha = defineModel('senha');


</script>

<template>
  <div class="container">
    <form>
      <section class="full-name">
          <Input label="Nome" :input-value="Boolean(nome)" v-model="nome"/>
          <Input label="Sobrenome" :input-value="Boolean(sobrenome)" v-model="sobrenome"/>
      </section>
      <section class="username-age">
          <Input label="Nome de usuário" :input-value="Boolean(username)" v-model="username"/>
          <Input label="Idade" :input-value="Boolean(idade)" v-model="idade"/>
      </section>
      <section class="credentials">
          <Input label="E-mail" :input-value="Boolean(email)" v-model="email"/>
          <Input label="Senha" :input-value="Boolean(senha)" v-model="senha"/>
      </section>
    <Button />
    </form>
  </div>
</template>

<style scoped>
.container {
  background: white;
  min-width: fit-content;
  height: fit-content;
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

.credentials {
  display: flex;
  flex-direction: column;
  gap: 8px;
}


</style>