<script setup>
defineProps([
    'nome', 'sobrenome', 'username', 'idade', 'email', 'senha'
])

</script>

<template>
  <section class="box">
    <div class="title">
      <div class="">
        <img class="icon" src="../../assets/icons/address-card.svg" alt="">
        <h2>Veja como ficará seu perfil</h2>
      </div>
      <span class="subtitle">Você pode editar suas informações após o registro</span>
    </div>
    <div class="container">
      <section class="user-info1">
        <div class="profile-picture"></div>
        <div class="nameInfo">
          <div>
            <div class="fullname" v-if="nome || sobrenome">{{ nome }} {{ sobrenome}}</div>
            <div class="fullnameNull" v-else>Nome Sobrenome</div>
            <div class="username" v-if="username"> @{{ username }}</div>
            <div class="usernameNull" v-else>@usuarioExemplo</div>
          </div>
          <div class="idade" v-if="idade">{{ idade }} anos</div>
          <div class="idadeNull" v-else>24 anos</div>
        </div>
      </section>
          <div class="email" v-if="email">
            <img src="../../assets/icons/mail-bulk.svg" alt="">
            <span>{{ email }}</span>
            </div>
          <div class="emailNull" v-else>
            <img src="../../assets/icons/mail-bulk.svg" alt="">
            <span>email-exemplo@email.com</span>
          </div>
          <div class="senha" v-if="senha" >
            <img src="../../assets/icons/lock.svg" alt="">
            <div>
              <span class="passDot" v-for="letra in senha.toString().split('')">.</span>
            </div>
          </div>
          <div class="senhaNull" v-else>
            <img src="../../assets/icons/lock.svg" alt="">
            <span class="passDot">...............</span>
          </div>
      <section>
      </section>
    </div>
  </section>

</template>

<style scoped>
.box {
  display: flex;
  flex-direction: column;
  gap: 8px;
  height: fit-content;
  user-select: none;
}

.title {
  margin: 0;
}

h2 {
  @media (max-width: 425px) {
    font-size: 1.3em
  }

  display: inline;
}

.subtitle {
  @media (max-width: 425px) {
    font-size: .9em;
  }
}

.container {
  display: flex;
  min-width: fit-content;
  height: fit-content;
  flex-direction: column;
  gap: 8px;
  background: white;
  padding: 1em;
  border-radius: 8px;
}

.user-info1 {
  display: flex;
  justify-content: flex-start;
  gap: 1em;
  width: 100%;
}

.profile-picture {
  background: #013159;
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
.nameInfo {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.fullname {
  font-size: 1.2rem;
}

.fullnameNull {
  font-size: 1.2rem;
  font-weight: 600;
  opacity: 75%;
}

.email {
  display: flex;
  gap: 8px;
}

.senha {
  display: flex;
  gap: 8px;
}

.emailNull, .senhaNull, .idadeNull, .usernameNull {
  display: flex;
  gap: 8px;
  opacity: 75%;
}

.passDot {
  font-size: 2rem;
  line-height: .1em;
}

</style>