<template>
<div class="container" @click="openLoginForm">
    <img src="../assets/icons/entrar.png" alt="">
    <h4>Iniciar / registrarse</h4>
</div>
</template>

<script lang="ts" setup>
import { useStore } from 'vuex';
const store = useStore();
const openLoginForm = () => {
    store.state.openLoginForm = true;
    store.state.closeLoginForm = false;
};
</script>

<style scoped>
.container {
    position: absolute;
    right: 10px;
    width: auto;
    height: 70%;
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 10px;
    background: #96FDA6;
    border-radius: 8px;
    cursor: pointer;
}

img {
    height: 20px;
    margin: 15px 0px 15px 5px;
}

h4 {
    color: #0CC958;
    font-family: sans-serif;
    margin: 15px 10px 15px 0px;
}
</style>