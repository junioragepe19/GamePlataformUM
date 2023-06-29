<script setup>
    const values = defineProps({
        image: {
            type: String,
            default: ''
        },
        color: {
            type: String,
            default: ''
        }
    })
    
</script>

<template>
    <img class="imageCard" :style="'box-shadow: -0.3rem 0.3rem 0px' + values.color" :src="values.image">
</template>

<style>
.imageCard{
    cursor: pointer;
    transition: 0.2s ease-in-out;
}
.imageCard:hover{
    transform: scale(1.1);
}
</style>