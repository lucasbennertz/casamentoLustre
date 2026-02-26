<template>
    <div class="imagem">
        <HeroTimer></HeroTimer>
    </div>
</template>

<script>
import HeroTimer from './temporizador/HeroTimer.vue'
export default {
    name: 'FundoImagem',
    components: {
        HeroTimer
    }
}
</script>

<style>
    .imagem{
        background-image: url('../../assets/foto_pre-weeding.webp');
        background-size: cover;
        background-position: 0 -65dvh;
        height: 100dvh;
        width: 100%;
        position: relative;

        }
</style>