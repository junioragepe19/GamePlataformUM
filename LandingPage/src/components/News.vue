<script setup>
    import { computed, ref } from 'vue';
    const values = defineProps({
        url:{
            type: String
        },
        avatar:{
            type: String
        },
        name:{
            type: String
        },
        title:{
            type: String
        }
    })
    function activeHover(){
        isHoving.value = true
    }
    function desActiveHover(){
        isHoving.value = false
    }
    const isHoving = ref(false);
    const isHover = computed( () => {
        return isHoving.value
    })
</script>


<template>
    <div class="mainNews d-flex">
        
        <div class="d-flex imgNews">
            <div class="layerCover" @mouseenter="activeHover" @mouseout="desActiveHover" :class="isHover ? 'cover' : ''">
            </div>
            <img :src="url">
        </div>
        <div class="d-flex user d-flex-row">
            <img :src="avatar">
            <p>{{name}}</p>
        </div>
        <h1 class="titleNews">{{title}}</h1>
    </div>
</template>
    

<style>
@import '../app.scss';
.layerCover{
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: 0.2s ease-in-out;
    width: 100%;
    height: 100%;
    position: absolute;
     top: 0;
}
.cover{
    background-color: rgba(0, 0, 0, 0.8);
}
.cover::before{
    content: 'View Post';
}
.imgNews{
    position: relative;
    height: 50%;
    width: 100%;
    overflow: hidden;
}
.titleNews{
    margin-left: 2rem;
    font-size: 18px;
}
.user{
    margin-left: 2rem;
    gap: 1rem;
    align-items: center;
}
.mainNews{
    max-width: 25%;
    max-height: 25%;
    width: 20%;
    height: auto;
    flex-direction: column;
    gap: 1rem;
    font-family: 'Outfit';
    color: white;
    background: rgba(255, 255, 255, 0.03);
    border-bottom: 4px solid #99EE2D;
}

</style>