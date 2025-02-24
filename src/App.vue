<script setup>
import FormRegister from "@/components/Form/FormRegister.vue";
import CardUser from "@/components/User/CardUser.vue";
import { ref } from "vue";

const nome = ref('');
const sobrenome = ref('');
const username = ref('');
const idade = ref('');
const email = ref('');
const senha = ref('');
</script>

<template>
  <h1 class="title">Cadastre-se</h1>
  <section class="container">
      <FormRegister
          v-model:nome="nome"
          v-model:sobrenome="sobrenome"
          v-model:username="username"
          v-model:idade="idade"
          v-model:email="email"
          v-model:senha="senha"
      />
      <CardUser
          :nome="nome"
          :sobrenome="sobrenome"
          :username="username"
          :idade="idade"
          :email="email"
          :senha="senha"
      />
  </section>
</template>

<style>
.title {
  color: #013159;
  user-select: none;
}

.container {
  padding: 32px 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}
</style>
