<script setup>
import { ref } from 'vue';
import Menu from 'vue-material-design-icons/Menu.vue';
import { useScreen } from '@/composables/screen.js';

const { isMobile } = useScreen();

const menuAberto = ref(false);
</script>
<template>

  <div class="header">
    <div class="header-logo">
      <img src="@/assets/logo.png" alt="Logo" />
      <h1>Garagem</h1>
    </div>

    <div class="models" >
      <router-link class="link" to="/">Home</router-link>
      <router-link class="link" to="/acessorios">Acessórios</router-link>
      <router-link class="link" to="/categorias">Categorias</router-link>
      <router-link class="link" to="/cores">Cores</router-link>
      <router-link class="link" to="/modelos">Modelos</router-link>
      <router-link class="link" to="/veiculos">Veículos</router-link>
    </div>
    <div class="login-out">
      <router-link class="link" to="/login">Login</router-link>
    </div>

    <Menu v-if="isMobile" class="menu-hamburger" @click="menuAberto = !menuAberto" />

  </div>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  width: 60%;
  height: 10vh;
  margin: auto;
  box-shadow: black 1px 1px 5px;
  border-radius: 10px;
}

.header-logo {
  width: 15%;
  display: flex;
}

.models {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 50%;
  font-size: 1.2rem;
}

.login-out {
  display: flex;
  align-items: center;
  
}

.link {
  text-decoration: none;
  color: inherit;
  font-size: 1.2rem;
}

</style>