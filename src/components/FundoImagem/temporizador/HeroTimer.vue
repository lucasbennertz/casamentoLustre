<template>
    <div class="quadro">
        <h1 id="title-quadro">Faltam:</h1>
        <div id="contador">
            <p><span id="meses"></span> Meses</p>
            <p><span id="dias"></span> Dias</p>
            <div id="horario">
                <p><span id="horas"></span></p> :
                <p><span id="minutos"></span></p> :
                <p><span id="segundos"></span></p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HeroTimer'
    }
    const targetDate = new Date('2026-10-17T09:30:00').getTime();

    const intervalo = setInterval(function() {
    const agora = new Date().getTime();
    const distancia = targetDate - agora;

    
    const meses = Math.floor(distancia / (1000 * 60 * 60 * 24 * 30.44));
    
    const dias = Math.floor((distancia % (1000 * 60 * 60 * 24 * 30.44)) / (1000 * 60 * 60 * 24));
    
    const horas = Math.floor((distancia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutos = Math.floor((distancia % (1000 * 60 * 60)) / (1000 * 60));
    const segundos = Math.floor((distancia % (1000 * 60)) / 1000);

    document.getElementById("meses").innerHTML = meses.toString().padStart(2, '0');
    document.getElementById("dias").innerHTML = dias.toString().padStart(2, '0');
    document.getElementById("horas").innerHTML = horas.toString().padStart(2, '0');
    document.getElementById("minutos").innerHTML = minutos.toString().padStart(2, '0');
    document.getElementById("segundos").innerHTML = segundos.toString().padStart(2, '0');

    if (distancia < 0) {
        clearInterval(intervalo);
        document.getElementById("contador").innerHTML = "Chegou o grande dia!";
    }
    }, 1000);
</script>

<style scoped>
    .quadro{
        background-color: rgba(255, 255, 255, 0.4);
        border: 1px solid rgba(255, 255, 255, 0.2);
        backdrop-filter: blur(10px);
        width: 50%;
        height: 40dvh;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 2dvw;
        display: flex;
        flex-direction: column;
        padding: 3dvh 3dvw;
    }
    #title-quadro{
        font-family: Georgia, 'Times New Roman', Times, serif;
        font-size: 3dvw;
        color: #2c3e50;
    }
    #contador{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
    }
    #contador span{
        font-size: 2.5dvw;
        color: #000000;
    }
    #contador p{
        display: flex;
        flex-direction: column;
        margin: 0 0.5dvw;
        height: 50%;
        width: 20%;
        padding: 0 1dvw;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 1dvw;
        background-color: rgba(63, 56, 56, 0.4);
        position: relative;
    }
    #horario{
        font-size: 2.5dvw;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
    }
</style>