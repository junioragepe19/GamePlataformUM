<template>
  <Header class="header" />
  <Hero />
  <div>
    <Populars url="/src/assets/Character.png" entry="Free" mode="1V1" prize="650" subtitle='League Of Legends' />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue';
import Populars from '@/components/Populars.vue';
import Hero from '@/components/Hero.vue';
</script>

