<script setup>
import FormRegister from "@/components/FormRegister.vue";
import CardUser from "@/components/CardUser.vue";
import {onMounted, ref} from "vue";

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
  margin: 0 0 24px 0;
  user-select: none;

  @media (max-width: 425px) {
    font-size: 1.7em;
  }
}

.container {
  padding: 32px 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}
</style>
