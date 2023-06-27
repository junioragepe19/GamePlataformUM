<script setup>
    import CustomButton from './CustomButton.vue';
    import { ref, watch } from 'vue';
    var countDownDate = new Date("June 28, 2023 17:00:00").getTime();
    var hours = ref(10);
    var minutes = ref(24);
    var seconds = ref(60);
    var isVideoPlaying = ref(false);
    const formattedTime = ref('12');
    var isfinished = ref(true)
    var interval = setInterval(function(){
        var countDownToday = Date.now();
        var difference = countDownDate - countDownToday;
        hours.value = Math.floor(difference / 3600000)
        minutes.value = Math.floor((difference / 60000) % 60)
        seconds.value = Math.floor((difference / 1000) % 60 )
        if (difference < 0)
            clearInterval(x);
            isfinished.value = true;
        
    },990)

    function fixNumber(number) {
        if(number < 10){
            return '0' + number
        }
        return number
    }
    watch([hours, minutes, seconds],([newHours, newMinutes, newSeconds]) => {
        newHours = fixNumber(newHours)
        newMinutes = fixNumber(newMinutes)
        newSeconds = fixNumber(newSeconds)
        formattedTime.value = `${newHours}:${newMinutes}:${newSeconds}`;
    })
    
    function stopVideo(){
        isVideoPlaying.value = false;
    }
    function playVideo(){
        isVideoPlaying.value = true;
        document.getElementById('video').play();
    }
</script>

<template>
    <div class="background d-flex flex-column">
        <h1 class="bgtitle d-flex">
            All the kings are fighting
        </h1>
        <p class="subtitle">Hurry to join in the greatest Valorant tournament of all time. Fight till the end and get the reward</p>
            <div class="blur"></div>  
            <div class="character">
                  
                <img class="img" src="../assets/Phoenix.png" />
            </div>
        
        <div class="polygon">
        </div>
        <div class="content_video">
            <div class="formatRight"></div>
            <div class="formatBottom2"></div>
            <div class="formatLeft"></div>
            <div class="formatBottom"></div>
            <div class="format d-flex">
                <p class="date">June</p>
                <p class="dateNumber">28</p>
                <p class="dateFull">{{ isfinished ? formattedTime : "Expired" }}</p>
            </div>
            <div class="format2 d-flex">
                <div v-if="!isVideoPlaying" class="play d-flex">
                    <div class="componentPlay d-flex" @click="playVideo">
                        <v-icon color="#D2E041" size="large">mdi-play</v-icon>
                    </div>
                </div>
                <video class="video" id="video"
                @pause="stopVideo"
                @loadstart="this.volume=0.1"
                poster="https://i0.wp.com/thegamerstation.com/wp-content/uploads/2023/03/Valorant-oynarken-nasil-cevrimdisi-offline-gorunebilirim.png?fit=1200%2C675&ssl=1" width="180" height="140">
                    
                    <source src="../assets/Trailer.mp4" type="video/mp4">
                    
                </video>    
            </div>
            <custom-button class="button" />
            <div class="nameTournament">
                <p class="bntitle">Valorant Tournament</p>
            </div>
        </div>
    </div>
</template>

<style>
@import '../app.scss';

.nameTournament{
    display: flex;
    position:absolute;
    height: inherit;
    width: inherit;
    top: 14rem;
    left: 15rem;
}

.bntitle{
    font-family: 'bntitle';
    color:#fff;
    font-size: 3rem;
}
.button{
    margin-top: 9.2rem;
    margin-left: 23.5rem;
}
.componentPlay{
    z-index: 90;
    cursor: pointer;
    align-items: center;
    justify-content: center;
    height: 25%;
    width: 25%;
    background-color: rgba(0, 0, 0, 0.8);
    border-radius: 5px;
}
.play{
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    position: absolute;
}
.video{
    margin: auto;
}
.formatRight{
    position: absolute;
    left: 23rem;
    top: 10.3rem;
    height: 3.75rem;
    width: 5px;
    background-color: rgb(255, 255, 255, 0.07);
}
.formatBottom2{
    justify-content: center;
    position: absolute;
    left: 23rem;
    top: 10rem;
    right: 15rem;
    height: 5px;
    width: 12rem;
    background-color: rgb(255, 255, 255, 0.07);
}
.formatBottom{
    position: absolute;
    left: 15.3rem;
    top: 13.74rem;
    right: 14rem;
    height: 5px;
    width: 7.7rem;
    background-color: rgb(255, 255, 255, 0.07);
}
.formatLeft{
    position: absolute;
    left: 15rem;
    top: 0.24rem;
    right: 14rem;
    height: 13.8rem;
    width: 5px;
    background-color: rgb(255, 255, 255, 0.07);
}
.dateFull{
    font-family: 'bntitle';
    font-size: 2rem;
    color: #fff;
    opacity: 0.5;
}
.dateNumber{
    margin-top: -1rem;
    font-family: 'bntitle';
    font-size: 4rem;
    color: #bef970;
}
.date{
    padding-top: 1rem;
    font-family: 'bntitle'; 
    color: white !important;
    font-size: 2rem;
}
.content_video{
    position: absolute;
    left: 36rem;
    top: 15rem;
    height: 100%;
    width: 100%;
}
.format2{
    position: absolute;
    right: 15rem;
    left: 23rem;
    height: 10rem;
    width: 12rem;
    border-top-right-radius: 2px;
    border-bottom-right-radius: 2px;
    background-color: rgb(255, 255, 255, 0.05);
}
.format2::before {
    content: "";
    position: absolute;
    top: 0px;
    width: calc(100%);
    height: 4px;
    background-color: rgb(255, 255, 255, 0.07);
}
.format{
    align-items: center;
    flex-direction: column;
    box-sizing: content-box;
    position: absolute;
    border-top-left-radius: 2px;
    border-bottom-right-radius: 2px;
    border-bottom-left-radius: 2px;
    right: 15rem;
    left: 15rem;
    height: 10rem;
    width: 8rem;
    border-bottom: rgb(255, 255, 255, 0) solid 4rem;
    background-color: rgb(255, 255, 255, 0.05);
}
.format::before {
    content: "";
    position: absolute;
    top: 0px;
    width: calc(100%);
    height: 4px;
    background-color: rgb(255, 255, 255, 0.07);
}
.polygon{
    transform: rotate(45deg);
    position: absolute;
    right: 10rem;
    height: 10rem;
    width: 10rem;
    flex-shrink: 0;
    background-color: #bef970;
    box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
-webkit-box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
-moz-box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
}
.character{
    height: 100%;
    width: 80%;
}
.img{
    transform: rotate(8.15deg);
    top: 13rem;
    left: 27.8rem;
    position: absolute;
    height: 80%;
}
.subtitle{
    position: relative;
    width: 33%;
    height: 50%;
    color: #fff;
    font-family: 'Outfit';
    font-size: 1.1rem;
}
.bgtitle{
    position: relative;
    width: 60%;
    height: 75%;
    font-family: 'bntitle';
    color: white;
    font-size: 8rem;
    line-height: 8rem;
}
.background{
    padding: 2rem;
    padding-left: 4rem;
    padding-top: 10rem !important;
    background-image: url('../assets/BgImage.png');
    background-position: 100%;
    background-size:cover;
    height: 100vh;
    width: 100%;
}
</style>