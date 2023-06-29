<script setup>
import InteractiveButton from './InteractiveButton.vue';

</script>

<template>
    <div class="bcOrgMain">
        <div class="shape">
            <img class="imgOrganization" src="../assets/organization.png" />
            <div class="shape1"></div>
            <div class="shape2"></div>
        </div>
        
        <div class="bcOrgText">
            <h1>Become an Organizer</h1>
            <p class="subtitleBrowse">Create a Space for free to host your own competitions, build a membership community and monetize.</p>
            <InteractiveButton class="BcOrgButton" text-button="Create Space Now" color="#99EE2D" color-text="black"/>
        </div>
    </div>
</template>

<style>
    @import '../app.scss';
    .BcOrgButton{
        max-height: 20%;
        max-width: 50%;
    }
    .bcOrgText{
        width: 40%;
        color: white;
    }
    .bcOrgText h1{
        font-family: 'bntitle';
        font-size: 3rem;
    }
    .bcOrgText p{
        width: 50%;
    }
    .bcOrgMain{
        gap: 4rem;
        display: flex;
        flex-direction: row;
    }
    .imgOrganization{
        padding-left: 11rem;
        position: relative;
        z-index: 12 !important;
    }
    .shape{
        position: relative;
        width: 60%;
        height: 10% !important;
    }
    .shape1{
        position: absolute;
        clip-path: polygon(39% 6%, 88% 15%, 95% 66%, 100% 100%, 0 100%, 0% 60%, 0 0);
        background-color: #D4FD99;
        top: 4rem;
        width: 100%;
        height: 77.5%;
        z-index: 11;
    }
    .shape2{
        position: absolute;
        top: 2rem;
        clip-path: polygon(39% 6%, 88% 15%, 100% 39%, 100% 100%, 0 100%, 0% 60%, 0 0);
        background-color: #99EE2D;
        height: 80%;
        width: 80%;
        z-index: 10;
    }
</style>