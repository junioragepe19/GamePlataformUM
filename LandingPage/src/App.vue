<template>
  <Header class="header" />
  <home />
  <Populars />
</template>

<script setup>
import Header from './components/Header.vue';
import Home from './views/Home.vue';
import Populars from './components/Populars.vue';
  //
</script>

<style>
body{
  background-color: black;
  width: 100%;
  height: 100%;
}
</style>
