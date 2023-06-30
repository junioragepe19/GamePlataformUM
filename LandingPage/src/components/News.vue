<script setup>

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

</script>


<template>
    <div class="mainNews d-flex">
        <img :src="url">
        <div class="d-flex user d-flex-row">
            <img :src="avatar">
            <p>{{name}}</p>
        </div>
        <h1 class="titleNews">{{title}}</h1>
    </div>
</template>
    

<style>
@import '../app.scss';

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