<script setup>
    import CustomButton from './CustomButton.vue';
    import { ref, watch } from 'vue';
    import { useDisplay } from 'vuetify/lib/framework.mjs';
    import InteractiveButton from './InteractiveButton.vue';
    var countDownDate = new Date("July 15, 2023 17:00:00").getTime();
    var hours = ref(10);
    var minutes = ref(24);
    var seconds = ref(60);
    var isVideoPlaying = ref(false);
    const formattedTime = ref('12');
    var isfinished = ref(true)
    const {width, mobile} = useDisplay()
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
    }
</script>

<template>
    <div class="background d-flex" :style="mobile ? 'flex-direction: column' : ''" >
        <div class="firstSection d-flex flex-column">
            <h1 class="bgtitle d-flex">
                All the kings are fighting
            </h1>
            <p class="subtitleHero">Hurry to join in the greatest Valorant tournament of all time. Fight till the end and get the reward</p>
                <div class="blur"></div> 
                <div class="character">
                    
                    <img class="img" src="../assets/Phoenix.png" />
                </div>
        </div>
        <div class="d-flex secondSection">
            <div class="contentSection">
            <div class="polygon">
            </div>
            <div class="content_video">
                <div class="format d-flex">
                    <div class="d-flex dateTournament">
                        <p class="date">July</p>
                        <p class="dateNumber">15</p>
                        <p class="dateFull">{{ isfinished ? formattedTime : "Expired" }}</p>
                    </div>
                    <div class="format2 d-flex d-flex-column">
                        
                        <v-dialog
                        transition="dialog-bottom-transition"
                        width="auto"
                      >
                        <template v-slot:activator="{ props }">
                            <div class="imgVideo" v-bind="props">
                                <div v-if="!isVideoPlaying" class="play d-flex">
                                    <div class="componentPlay d-flex" @click="playVideo">
                                        <v-icon color="#D2E041" size="large">mdi-play</v-icon>
                                    </div>
                                </div>
                                <img @click="isActive.value = true"
                                src="https://i0.wp.com/thegamerstation.com/wp-content/uploads/2023/03/Valorant-oynarken-nasil-cevrimdisi-offline-gorunebilirim.png?fit=1200%2C675&ssl=1" class="imgVideoContent"/>
                            </div>
                        </template>
                        <template v-slot:default="{ isActive }">
                            <video
                            @pause="stopVideo"
                            autoplay
                            @loadstart="this.volume=0.1"
                            poster="https://i0.wp.com/thegamerstation.com/wp-content/uploads/2023/03/Valorant-oynarken-nasil-cevrimdisi-offline-gorunebilirim.png?fit=1200%2C675&ssl=1">
                                
                                <source src="../assets/Trailer.mp4" type="video/mp4">
                            </video>
                        </template>
                      </v-dialog>
                         
                    </div>
                </div>
                <!-- <div class="join">
                    <interactive-button text-button="Join Tournament" :is-icon='true' color-text="black" color="#99EE2D" icon="mdi-arrow-right-thick" />
                </div>  -->
                <!-- <div class="nameTournament">
                    <p class="bntitle">Valorant Tournament</p>
                </div> -->
            </div>
        </div>
        </div>
    </div>
</template>

<style>
@import '../app.scss';
.imgVideoContent{
    width: 100%;
    height: 100%;
}
.imgVideo{
    width: 100%;
    height: 100%;
}
.firstSection{
    position: relative;
    width: 100%;
}
.dateTournament{
    display: flex;
    flex-direction: column;
    width: 35%;
    align-items: center;
}
.contentSection{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: right;
    position: absolute;
    right: 0;
    top: 0;
}
.join{
    position: absolute;
    width: 50%;
    right: 0;
    height: 15% !important;
}
.secondSection{
    position: relative;
    width: 60%;
    height: 100vh;
}
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
    flex-wrap: wrap;
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
    width: 100%;
    height: 100%;
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
    position: relative;
    display: flex;
    justify-content: right;
    margin-right: 15%;
    top: 10%;
    width: 100%;
    height: 100%;
}
.format2{
    position: absolute;
    right: 4%;
    top: 10%;
    height: 44%;
    width: 56%;
}
.format{
    clip-path: polygon(50% 0%, 100% 0, 100% 63%, 37% 62%, 37% 100%, 0 100%, 0 0);
    position: absolute;
    height: 45%;
    width: 75%;
    background-color: rgb(255, 255, 255, 0.05);
    border: 0.3rem solid rgba(255, 255, 255, 0.3);
}
.polygon{
    transform: rotate(45deg);
    position: absolute;
    height: 10rem;
    width: 10rem;
    top: 0;
    right: 10%;
    flex-shrink: 0;
    background-color: #bef970;
    box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
    -webkit-box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
    -moz-box-shadow: 1px 1px 96px 10px rgba(190,249,112,0.75);
}
.character{
    height: 100%;
    width: 100%;
}
.img{
    transform: rotate(8.15deg);
    top: 7%;
    left: 52%;
    position: absolute;
    height: 100%;
}
.subtitleHero{
    position: relative;
    padding: 1%;
    width: 33%;
    height: 50%;
    color: #fff;
    font-family: 'Outfit';
    font-size: 1.1rem;
}
.bgtitle{
    width: 100%;
    height: 50%;
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
    height: 100%;
    width: 100%;
}
</style>