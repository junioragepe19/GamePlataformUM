<script setup>

    defineProps({
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
    })
</script>

<template>
    <div class="d-flex">
        <div class="tournament">
            <div class="title">
                <p class="bntitle black">Path <br>to Power</p>
                <p class="subtitle">{{subtitle}}</p>
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
                </div>
            </div>
        </div>
    </div>
</template>

<style>
@import '../app.scss';
.titleTopic{
    opacity: 0.6000000238418579;
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
    width: inherit;
    height: 4rem;
    background-color: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(7.5px);
}
.subtitle{
    width: initial;
    font-family: 'Outfit';
    color: black;
    font-size: 1rem;
}
.title{
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
    width: 18rem;
    height: 22rem;
    background-color: #BEF970;
    clip-path: polygon(56% 0, 78% 0, 100% 18%, 100% 100%, 71% 100%, 49% 100%, 0 100%, 0% 70%, 0 35%, 0 0);

}
</style>