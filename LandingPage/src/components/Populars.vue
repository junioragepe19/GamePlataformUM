<script setup>
    import InteractiveButton from './InteractiveButton.vue'
    import { computed } from 'vue';
    const props = defineProps({
        url: {
            type: String, default: ''},
        title: {
            type: String, default: ''},
        subtitle: {
            type: String, default: ''},    
        entry: {
            type: String, default: ''},
        mode: {
            type: String, default: ''},
        prize: {
            type: String, default: ''},
        color: {
            type: String, default: ''},
        colorText: {
            type: String, default: ''},
    })
    const textReplaced = computed(() => {
        return props.title.replace(/\\n/g, '\n') })
    const subtextReplaced = computed(() => {
        return props.subtitle.replace(/\\n/g, '\n') })
</script>

<template>
    <div class="d-flex general">
        <div class="tournament" :style="color">
            <div class="title">
                <p class="bntitle" :style="colorText">{{textReplaced}}</p>
                <p class="subtitle" :style="colorText">{{subtextReplaced}}</p>
            </div>
            <div class="d-flex imglayer">
            <img class="imgtour" :src="url" />
            </div>
            <div class="mainInfo">
                <div class="infos d-flex">
                    <div class="topic">
                        <h1 class="titleTopic">Entry</h1>
                        <p class="valueTopic">{{entry}}</p>
                    </div>
                    <div class="topic">
                        <h1 class="titleTopic">Mode</h1>
                        <p class="valueTopic">{{mode}}</p>
                    </div>
                    <div class="topic">
                        <h1 class="titleTopic">Prize</h1>
                        <p class="valueTopic">${{prize}}</p>
                    </div>
                    <div class="interactive">
                    <InteractiveButton />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
@import '../app.scss';
.interactive{
    width: 35%;
    height: 100%;
    display: flex;
    align-items: center;
}

.general{
    width: 25%;
    height: 100%;
}
.titleTopic{
    opacity: 0.75;
    font-size: 16px;
}
.valueTopic{
    font-size: 14px;
}
.topic{
    color: white;
    font-family: 'Outfit';
}
.mainInfo{
    position: absolute;
    top: 0;
    width: inherit;
    height: inherit;
    display: flex;
    align-items: flex-end;
}
.infos{
    gap: 1rem;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: inherit;
    height: 4rem;
    background-color: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(7.5px);
}
.subtitle{
    width: initial;
    font-family: 'Outfit';
    font-size: 1rem;
    margin-top: 0.5rem;
    line-height: 1.3rem;
}
.title{
    white-space: pre-line;
    margin-left: 1.2rem;
    margin-top: 1.2rem;
    line-height: 3rem;
}
.black{
    color: black;
}
.bntitle{
    font-family: 'bntitle';
}
.imglayer{
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: inherit;
    align-items: end !important;
    justify-content: end;

}
.imgtour{
    width: 100%;
}
.tournament{
    position: relative;
    width: 100%;
    height: 100%;
    clip-path: polygon(56% 0, 78% 0, 100% 18%, 100% 100%, 71% 100%, 49% 100%, 0 100%, 0% 70%, 0 35%, 0 0);

}
</style>