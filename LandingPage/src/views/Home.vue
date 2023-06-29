<template>
  <Header class="header" />
  <Hero />
  <div class="d-flex w-full titlePopular">
    <div class="titlePopular">Popular Tournaments</div>
    <p class="view">View All</p>
  </div>
  <div class="d-flex d-flex-column populars">
    <Populars :url="Ashe" entry="Free" color="background-color: #BEF970" colorText="color: #000" mode="1V1" prize="650" title="Path\nto Power" subtitle='League Of Legends' />
    <Populars :url="Pubg" entry="Free" color="background-color: #E6F0D8" colorText="color: #000" mode="2V2" prize="50" title="Dutiful\nDeathMatch" subtitle='Playerunknown`s\nBattlegrounds ' />
    <Populars :url="Val" entry="Free" color="background-color: #46800A" colorText="color: #fff" mode="2V2" prize="650" title="Open fire all\nStars" subtitle='Valorant' />
    <Populars :url="Counter" entry="Free" color="background-color: #E6F0D8" colorText="color: #000" mode="5V5" prize="650" title="Cyl\nCSGO" subtitle='Counter Strike\nGlobal Offensive' />
  </div>
</template>

<style>
  @import '../app.scss';

  .view{
    text-align: right;
    color: white;
    border-bottom: 2px solid #BEF970;
  }
  .titlePopular{
    justify-content: space-between;
    margin-left: 2rem;
    margin-right: 2rem;
    margin-bottom: 1rem;
    font-family: 'Outfit';
    color: white;
    font-weight: bold;
    font-size: 1.3rem;
  }
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

