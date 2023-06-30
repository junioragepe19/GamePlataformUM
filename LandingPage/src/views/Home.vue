<script setup>
import BrowseGames from '@/components/BrowseGames.vue';
import Ashe from '../assets/Character.png';
import Pubg from '../assets/Pubg.png';
import Val from '../assets/Omen.png';
import Counter from '../assets/CS.png';
import Header from '@/components/Header.vue';
import Populars from '@/components/Populars.vue';
import Hero from '@/components/Hero.vue';
import HorizonPost from '../assets/HorizonPost.png'
import CallPost from '../assets/CallPost.png'
import GTAPost from '../assets/GTAPost.png'
import TombPost from '../assets/TombPost.png'
import Avatar1 from '../assets/Avatar.svg';
import Avatar2 from '../assets/Avatar1.svg';
import Avatar3 from '../assets/Avatar2.svg';
import Avatar4 from '../assets/Avatar3.svg';
import BecomeOrganizator from '@/components/BecomeOrganizator.vue';
import { computed, ref } from 'vue';
import News from '@/components/News.vue';
import InteractiveButton from '@/components/InteractiveButton.vue';

const isHoving = ref(false);

function activeHover(){
  isHoving.value = true
}

function desActiveHover(){
  isHoving.value = false;
}
const valueHover = computed( () => {
  return isHoving.value; })
</script>

<template>
  <Header class="header" />
  <Hero />
  <div class="d-flex w-full titlePopular">
    <div class="titlePopular">Popular Tournaments</div>
    <p class="view">View All</p>
  </div>
  <div class="d-flex d-flex-column populars">
    <Populars class="popular" @mouseenter="activeHover" @mouseleave="desActiveHover" :class="valueHover ? 'nothover' : ''" :url="Ashe" entry="Free" color="background-color: #BEF970" colorText="color: #000" mode="1V1" prize="650" title="Path\nto Power" subtitle='League Of Legends' />
    <Populars class="popular" :url="Pubg" entry="Free" @mouseenter="activeHover" @mouseleave="desActiveHover" :class="valueHover ? 'nothover' : ''"  color="background-color: #E6F0D8" colorText="color: #000" mode="2V2" prize="50" title="Dutiful\nDeathMatch" subtitle='Playerunknown`s\nBattlegrounds ' />
    <Populars class="popular" :url="Val" entry="Free" @mouseenter="activeHover" @mouseleave="desActiveHover" :class="valueHover ? 'nothover' : ''" color="background-color: #46800A" colorText="color: #fff" mode="2V2" prize="650" title="Open fire all\nStars" subtitle='Valorant' />
    <Populars class="popular" :url="Counter" entry="Free" @mouseenter="activeHover" @mouseleave="desActiveHover" :class="valueHover ? 'nothover' : ''" color="background-color: #E6F0D8" colorText="color: #000" mode="5V5" prize="650" title="Cyl\nCSGO" subtitle='Counter Strike\nGlobal Offensive' />
  </div>
  <BrowseGames class="browseGames"/>
  <BecomeOrganizator class="organization"/>
  <div class="newsSection">
    <div class="d-flex d-flex-row newsMenu">
      <div class="d-flex d-flex-row navMenu">
        <div class="titleSectionNews">News</div>
        <div class="d-flex d-flex-row menuOptions">
          <button value="latest">
            Latest
          </button>
          <button value="game">
            Game
          </button>
          <button value="tournament"> 
            Tournaments
          </button>
          <button value="xbox">
            Xbox
          </button>
          <button value="xbox">
            PC
          </button>
        </div>
      </div>
      <div class="input">
        <input placeholder="Search"/>
        <v-icon class="iconInput">mdi-magnify</v-icon>
      </div>
    </div>
    <div class="d-flex d-flex-row news">
      <News  :url="HorizonPost" :avatar="Avatar1" name="Avery Jackson" title="Unveiling the Hidden Wonders of Nature: Exploring the World Beyond the Horizon"  />
      <News  :url="CallPost" :avatar="Avatar2" name="Jerome Mckinney" title="A New Era of Call of Duty Warfare"  />
      <News  :url="GTAPost" :avatar="Avatar3" name="Angel Richards" title=" Exploring the Beauty of the Great Outdoors"  />
      <News  :url="TombPost" :avatar="Avatar4" name="Bobby Harrison" title="Shadows of Destiny - Unraveling Ancient Mysteries"  />
    </div>
    <div class="buttonNews">
      <InteractiveButton class="buttonMoreNews" :isIcon="true" icon="mdi-plus" textButton="Load More" color="white" colorText="black" />
    </div>
  </div>
</template>

<style>
  @import '../app.scss';
  .buttonMoreNews{
    width: 10%;
    margin-bottom: 2rem;
  }
  .buttonNews{
    display: flex;
    justify-content: center;
    margin-top: 2rem;
    width: 100%;
    height: 20%;
  }
  .navMenu{
    margin-bottom: 1.5rem;
  }
  .menuOptions{
    gap: 2rem;
  }
  .iconInput{
    right: 0.2rem;
    position: absolute;
    color: white;
    z-index: 10;
  }
  .input{
    margin-bottom: 1.5rem;
    position: relative;
    font-family: 'Outfit';
    border-bottom: 1px solid white;
    color: white;
  }
  input{
    padding-right: 2rem;
    padding-left: 0.5rem;
    color: white !important;
  }
  button:focus{
    border-bottom: 1px solid #BEF970;
  }
  .titleSectionNews{
    margin-right: 3rem;
    font-family: 'Outfit';
  }
  .newsMenu{
    margin-bottom: 1rem;
    margin: 0 auto;
    width: 83%;
    justify-content:space-between;
    font-family: 'bnTitle';
    color: white;

  }
  .organization{
    margin-bottom: 5rem;
  }
  .news{
    justify-content: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .browseGames{
    height: 50%;
  }
  .view{
    text-align: right;
    color: white;
    border-bottom: 2px solid #BEF970;
  }
  .popular{
    transition: 0.2s ease-in-out;
  }
  .popular:hover{
    transform: scale(1.02);
    z-index: 11;
    filter: grayscale(0) !important;
  }
  .nothover{
    filter: grayscale(1);
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
    height: 60vh;
    margin-bottom: 5rem;
  }
</style>


