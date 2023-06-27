<template>
    <div class="button">
        <div class="text">
            <div class="d-flex nameButton">
                <p>Join Tournament</p>
                <v-icon class="icon" color="black">mdi-arrow-right-thick</v-icon>
            </div>
        </div>
        <div class="bg"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
    </div>
</template>


<style>
@import '../app.scss';

.text{
    z-index: 40;
    position: absolute;
    top: 13%;
    display: flex;
    width: 94%;
    height: 39%;
    text-align: center;
    font-size: 1.5rem;
    font-family: 'bntitle';
}
.nameButton{
    margin: auto;
}

.button{
    position: absolute;
    width: 13rem;
    height: 9.2rem;
}
.icon{
}
.bg1{
   position: absolute;
   width: 29%;
   height: 18.91%;
   background-color: #99EE2D;
   left: 79.9%;
   top: 33.2%; 
}
.bg{
    transform: rotate(-45deg);
    position: absolute;
    top: 15%;
    right: -4%;
    width: 14%;
    height: 30% !important;
    height: inherit;
    background-color: #99EE2D;
}

.bg2{
    width: 94%;
    top: 13%;
    height: 39%;
    position: absolute;
    background-color: #99EE2D;
}
</style>