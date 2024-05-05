<template>
  <div class="container-app">
    <div class="menu">
      <div class="container-img-nav">
        <router-link to="/">
          <img class="logo-img" src="./assets/logo.png" alt="">
        </router-link>
        <nav>
          <router-link to="/mis-envios" class="nav-link button-1" :class="{ 'active': $route.path === '/mis-envios' }">
            <img src="./assets/icons/paquete.png" alt="">
            <h3>Mis envíos</h3>
          </router-link>
          <div class="line"></div>
          <router-link to="/hacer-envio" class="nav-link button-2"
            :class="{ 'active': $route.path === '/hacer-envio' }">
            <img src="./assets/icons/camion.png" alt="">
            <h3>Hacer envío</h3>
          </router-link>
          <div class="line"></div>
          <router-link to="/novedades" class="nav-link button-3" :class="{ 'active': $route.path === '/novedades' }">
            <img src="./assets/icons/altavoz.png" alt="">
            <h3>Novedades</h3>
          </router-link>
        </nav>
      </div>
    </div>
    <div class="content">
      <div class="head-content">
        <LoginRegisterButton />
      </div>
      <div class="body-content">
        <router-view />
      </div>
    </div>
    <!-- Modal container -->
    <div class="modal-container" ref="modalContainer"></div>
  </div>
</template>

<script lang="ts" setup>
import LoginRegisterButton from './components/LoginRegisterButton.vue';
import LoginForm from './components/LoginForm.vue';
import { onBeforeMount, ref, watch, createApp } from 'vue';
import { useRouter } from 'vue-router';
import { useStore } from 'vuex';

// DEFINICIÓN DE CONSTANTES
const modalContainer = ref();  // // Contenedor de modals
const router = useRouter();
const store = useStore();

// CONFIGURACIÓN ANTES DE MONTAR EL APP
onBeforeMount(() => {
  router.push('/');
});

watch(() => store.state.openLoginForm, () => {
  if (store.state.openLoginForm == true) {
    // CREAMOS UNA INSTANCIA DE 'LoginForm'
    const loginForm = createApp(LoginForm);
    // SI EL ELEMENTO '<div class="modal-container"></div>' AL QUE 'modalContainer' HACE REFERENCIA, EXISTE 
    if (modalContainer.value) {
      // MONTAMOS LA INSTANCIA DE 'LoginForm' EN EL ELEMENTO QUE REFERENCIA 'modalContainer'
      loginForm.mount(modalContainer.value);
    }
  }
})

watch(() => store.state.closeLoginForm, () => {
  console.log("Se detecó un cambio en Closeloginform")
  if (store.state.closeLoginForm == true) {
    const container = modalContainer.value;
    if (container) {
      container.innerHTML = '';
    }
    store.state.closeLoginForm = false;
    console.log("Eliminando value de modal container")
  }
})


</script>

<style scoped>
.container-app {
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: row;
  background: #f0f0f0;
}

.menu {
  position: fixed;
  width: 15%;
  height: 100vh;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 0 24px 24px 0;
}

.menu .container-img-nav {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-rows: 0.25fr 0.75fr;
  place-items: center;
  border-radius: 0 24px 24px 0;
}

.container-img-nav .nav-link:nth-child(0) {
  cursor: pointer;
}

.container-img-nav .nav-link:nth-child(0) img {
  grid-row: 1 / 2;
  width: 70%;
  height: auto;
}

.container-img-nav nav {
  grid-row: 2 / 3;
  width: 100%;
  height: 100%;
  background: #0A77F7;
  border-radius: 0px 0px 24px 0px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  gap: 20px;
}

.container-img-nav nav .line {
  width: 85%;
  height: 2px;
  background: #0B5DFD;
}

.container-img-nav nav .nav-link:nth-child(1) {
  margin-top: 20px;
}

.nav-link {
  width: 85%;
  height: 50px;
  background: rgba(255, 255, 255, 0.1);
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 15px;
  text-decoration: none;
  transition: background ease-in-out 0.3s;
  border-radius: 8px;
}

.nav-link img {
  width: 25px;
}

.nav-link h3 {
  color: white;
  font-size: 18px;
  font-family: 'Arial', sans-serif;
  font-weight: bold;
}

.nav-link:hover,
.active {
  background: #0B5DFD;
}

.content {
  position: absolute;
  right: 0px;
  width: 85%;
  height: 100%;
  background: #f0f0f0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  gap: 20px;
  overflow-y: scroll;
}

.content .head-content {
  position: relative;
  margin-top: 40px;
  width: 92%;
  height: 80px;
  border-radius: 8px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.content .body-content {
  margin-bottom: 40px;
  width: 92%;
  height: 100%;
  background: #fff;
  border-radius: 8px;
}

.modal-container {
  width: auto;
  height: auto;
  background: #000000b1;
  z-index: 100;
}
</style>
