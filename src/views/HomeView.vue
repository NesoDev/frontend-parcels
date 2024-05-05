<template>
    <div class="container-home">
        <img src="../assets/repartidor.png" alt="">
        <div class="container-title-description">
            <div class="title">
                <h2>SOMOS</h2>
                <h2>INTERCARGA</h2>
            </div>
            <p>
                Una empresa con años de experiencia
                en el mercado, siempre dedicándonos
                íntegramente en el rubro de traslado
                de unidades, caracterizándonos por
                su seguridad, puntualidad y rapidez.
            </p>
            <div class="social-media">
                <h3>Síguenos en:</h3>
                <img src="../assets/icons/redes.png" alt="">
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
</script>

<style scoped>
.container-home {
    position: relative;
    width: 100%;
    height: 100%;
    background: #d0d0d0;
    border-radius: 8px;
}

img {
    position: absolute;
    bottom: 0px;
    left: 20px;
    height: 90%;
    z-index: 1;
}

.container-title-description {
    position: absolute;
    right: 0px;
    width: 65%;
    height: 100%;
    display: flex;
    flex-direction: column;
}

.container-title-description .title {
    width: 100%;
    font-family: sans-serif;
    font-size: 45px;
    font-weight: bold;
    display: flex;
    flex-direction: row;
    gap: 20px;
    margin: 80px 0px 20px 0px;
}

.container-title-description .title h2:nth-child(1) {
    color: #414141;
    margin: 0;
}

.container-title-description .title h2:nth-child(2) {
    color: #0B5DFD;
    margin: 0;
}

.container-title-description p {
    position: absolute;
    top: 150px;
    right: 40px;
    width: 73%;
    height: auto;
    font-family: sans-serif;
    font-size: 30px;
    color: #99A0A9;
    text-wrap:balance;
}

.container-title-description .social-media {
    position: absolute;
    left: 160px;
    bottom: 40px;
    width: 100%;
    height: 80px;
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 10px;
}

.container-title-description .social-media h3 {
    margin: 0;
    font-family: sans-serif;
    font-size: 25px;
}

.container-title-description .social-media img {
    height: 40px;
    width: auto;
}


</style>