<template>
  <Header class="header" />
  <Hero />
  <div class="d-flex d-flex-column populars">
    <Populars :url="Ashe" entry="Free" color="background-color: #BEF970" colorText="color: #000" mode="1V1" prize="650" title="Path \nto Power" subtitle='League Of Legends' />
    <Populars :url="Pubg" entry="Free" color="background-color: #E6F0D8" colorText="color: #000" mode="2V2" prize="50" title="Dutiful DeathMatch" subtitle='Playerunknown`s Battlegrounds ' />
    <Populars :url="Val" entry="Free" color="background-color: #46800A" colorText="color: #fff" mode="2V2" prize="650" title="Open fire all Stars" subtitle='Valorant' />
    <Populars :url="Counter" entry="Free" color="background-color: #E6F0D8" colorText="color: #000" mode="5V5" prize="650" title="Cyl CSGO" subtitle='Counter Strike Global Offensive' />
  </div>
</template>

<style>
  .populars{
    width: 100%;
    height: 100vh;
  }
</style>
<script setup>
import Ashe from '../assets/Character.png';
import Pubg from '../assets/Pubg.png';
import Val from '../assets/Omen.png';
import Counter from '../assets/CS.png';
import Header from '@/components/Header.vue';
import Populars from '@/components/Populars.vue';
import Hero from '@/components/Hero.vue';
</script>

