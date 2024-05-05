<template>
    <div class="container">
        <div class="container-form">
            <img src="../assets/icons/exit.png" alt="" @click="closeLoginForm">
            <h3>Iniciar Sesión</h3>
            <div class="container-inputs">
                <div class="container-input">
                    <img src="../assets/icons/usuario.png" alt="">
                    <input type="text" placeholder="Nombre de usuario">
                </div>
                <div class="container-input">
                    <img src="../assets/icons/candado.png" alt="">
                    <input type="password" placeholder="Contraseña">
                </div>
            </div>
            <div class="container-button-register">
                <input type="submit" value="CONTINUAR">
                <div class="link">
                    <h4>¿No tienes una cuenta?</h4>
                    <h4>Regístrate</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import store from '@/store';

const closeLoginForm = () => {
    store.state.openLoginForm = false;
    store.state.closeLoginForm = true;
    console.log("Closeloginform ha cambiado a true")
}
</script>

<style scoped>
.container {
    width: 100vw;
    height: 100vh;
    display: grid;
    place-items: center;
}

.container-form {
    position: relative;
    width: auto;
    height: auto;
    background: #fff;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.container-form > img {
    position: absolute;
    top: 20px;
    right: 20px;
    height: 15px;
    width: auto;
    cursor: pointer;
}

.container-form h3 {
    font-family: sans-serif;
    font-size: 30px;
    font-weight: 600;
    color: #868686;
    margin: 0;
    margin-top: 35px;
}

.container-form .container-inputs {
    width: auto;
    height: auto;
    background: white;
    display: flex;
    flex-direction: column;
    gap: 30px;
    margin: 0px 35px 5px 35px;
}

.container-form .container-inputs .container-input {
    width: 250px;
    height: 50px;
    background: #fff;
    border-bottom: 2px solid #a4a4a4;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between
}

.container-form .container-inputs .container-input img {
    height: 30px;
    width: 30px;
}

.container-form .container-inputs .container-input input {
    height: 30px;
    width: 200px;
    border: none;
    outline: none;
    box-shadow: none;
    font-size: 18px;
}

.container-form .container-inputs .container-input input::placeholder {
    color: #a4a4a4;
}

.container-form .container-button-register {
    width: 250px;
    height: auto;
    margin-bottom: 40px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;
}

.container-form .container-button-register input {
    width: 100%;
    height: 50px;
    appearance: none;
    border: none;
    background: #0A77F7;
    font-size: 15px;
    font-weight: 600;
    color: #fff;
    border-radius: 4px;
    cursor: pointer;
}

.container-form .container-button-register .link {
    width: 90%;
    height: auto;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}

.container-form .container-button-register .link h4 {
    margin: 0;
    font-family: sans-serif;
    font-size: 14px;
    font-weight: 400;
}

.container-form .container-button-register .link h4:nth-child(1) {
    color: #686868;
}

.container-form .container-button-register .link h4:nth-child(2) {
    color: #3e92f2;
    cursor: pointer;
}
</style>