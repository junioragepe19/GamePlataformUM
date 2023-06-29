<script setup>
    const values = defineProps({
        textButton: {
            type: String,
            default: ''},
        isIcon: {
            type: Boolean,
            default: false
        },
        icon: {
            type: String,
            default: ''
        },
        color: {
            type: String,
            default: ''
        },
        colorText: {
            type: String,
            default: ''
        }
        })
</script>


<template>
    <div class="buttonInterative" :style="'background-color: ' + values.color + ';color: ' + values.colorText">
    <p>{{values.textButton}}</p>
    <v-icon v-if="values.isIcon">{{values.icon}}</v-icon>
    
    </div>
</template>

<style>
@import '../app.scss';


.buttonInterative{
    font-family: 'bntitle';
    font-size: 1.3rem;
    gap: 8;
    display: flex;
    justify-content:center;
    align-items: center;
    clip-path: polygon(68% 0, 100% 49%, 100% 100%, 0 100%, 0 0);
    width: 100%;
    height: 68%;
}
</style>