<script setup>
import Fifa from '../assets/fifaCapa.png'
import Valorant from '../assets/valorantCapa.png'
import LoL from '../assets/lolCapa.png'
import CardGame from './CardGame.vue';
</script>

<template>
    <div class="d-flex d-flex-row">
        <div class="textBrowse">
        <h1 class="titleBrowse">Play your best game and collect rewards</h1>
        <h2 class="subtitleBrowse">
            Get ready to unlock a realm of rewards as you play your best game. 
            Every strategic move and every challenge overcome is an opportunity to collect valuable treasures. 
            With determination and skill, you'll become a true prize collector, reaching new heights of success on your journey. 
            Don't settle for anything less than what you deserve. Play with passion and reap the well-deserved benefits.</h2>
        </div>
        <div class="imagesBrowse d-flex">
            <CardGame class="imageBrowse" color="#bef970" :image="Fifa" />
            <CardGame class="imageBrowse" color="#F15D09" :image="LoL" />
            <CardGame class="imageBrowse" color="#F15D09" :image="Valorant" />
        </div>
    </div>

</template>

<style>
@import '../app.scss';
.imagesBrowse{
    gap: 2rem;
    width: 40%;
}
.imageBrowse{
    height: 60%;
}
.textBrowse{
    width: 40%;
    margin-left: 10%;
}
.titleBrowse{
    width: 80%;
    font-family: 'bntitle';
    font-size: 3rem;
    color: white;
}
.subtitleBrowse{
    width: 85%;
    text-align: justify;
    font-family: 'Outfit';
    opacity: 0.550000011920929;
    color: white;
    font-size: 1rem;
}
</style>