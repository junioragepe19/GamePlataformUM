<script setup>
import Logo from './Logo.vue';
// import axios from "axios";
// import { onBeforeMount } from 'vue';
import { ref } from 'vue';
const LanguageSelected = ref('English');
const RegionSelected = ref('United States')
const languages = ['English',
'Spanish',
'French',
'Russian',
'German',
'Arabic',
'Portuguese',
'Chinese',
'Hindi']
const countries = ['Bangladesh',
'Brazil',
'China',
'India',
'United States','Turkey']

const topics = ['About', 'Tournaments', 'Ladder', 'Shop', 'Community', 'Stream', 'Blog', 'Help Center']
const socialMedias = [{'name': 'Twitch', 'icon': 'mdi-twitch' },{'name':  'Instagram', 'icon':'mdi-instagram'},
{'name': 'Twitter', 'icon':'mdi-twitter'},{'name': 'Youtube','icon': 'mdi-youtube' }]
// const countries = onBeforeMount( () => {
//     axios.get("https://restcountries.com/v3.1/all")
//     .then((res) => {
//           console.log(res.data)
//     })
//     .catch((error) => {
//           console.log(error);
//     });
// })

</script>

<template>
    <footer>
        <div class="firstFooter">
            <Logo size-text="1.5rem" />   
            <p class="textFooter">Embark on a journey of limitless competition, 
                connections, and boundless excitement on this 
                revolutionary website, where the greatness of gaming finds its true home!</p>

            <p class="languageFooter">Language and Location</p>
            <div class="optionsFooter">
                <div class="language">
                    <v-select class="select"
                    v-model="LanguageSelected"
                    :items="languages">
                    </v-select>
                </div>
                <div class="language">
                    <v-select class="select"
                    v-model="RegionSelected"
                    :items="countries">
                    </v-select>
                </div>
            </div>
            <p class="textFooter mark">© 2023 UISMODE. All rights reserved.</p>
        </div>
        <div class="secondFooter">
            <div class="topics">
                <button class="topic" v-for="topic in topics">
                {{topic}}
                </button>
            </div>
            <div class="line"></div>
            <div>
                <div class="topics">
                    <button class="topic" v-for="social in socialMedias">
                    <v-icon>{{social.icon}}</v-icon>
                    {{social.name}}
                    </button>
                    <div class="terms">
                    <button class="term">Contact us</button>
                    <button class="term">Privacy Policy</button>
                    <button class="term">Terms & Conditions</button>
                 </div>
                </div>
                
            </div>
        </div>
    </footer>
</template>

<style>
    @import '../app.scss';
    button.term{
        text-align: start;
    }
    .terms{
        margin-top: 2rem;
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    .line{
        background-color: #99EE2D;
        height: 80%;
        margin-top: 5rem;
        width: 0.1%;
        
    }
    .topic{
        width: fit-content;
    }
    .topics{
        margin-left: 5rem;
        margin-top: 5rem;
        margin-right: 5rem;
        color: white;
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }
    .mark{
        padding-top: 5rem;
        opacity: 0.5;
    }
    .secondFooter{
        
        clip-path: polygon(0 0, 89% 0, 100% 18%, 100% 100%, 0 100%, 0% 50%);
        margin-left: 5rem;
        margin-right: 5rem;
        margin-top: 5rem;
        width: 40rem;
        height: 100%;
        display: flex;
        flex-direction: row;
        background: rgba(72, 77, 67, 0.10);
        backdrop-filter: blur(15px);
    }
    .optionsFooter{
        display: flex;
        gap: 1rem;
    }
    .v-field--variant-filled .v-field__overlay {
    background-color: rgba(0, 0, 0, 0) !important;
    }
    .mdi-menu-down::before {
        content: '\F0140' !important;
    }
    .language{
        width: 30%;
    }
    .select{
        color: white;
    }
    .languageFooter{
        margin-top: 3rem;
        font-family: 'Outfit';
        text-align: start;
        color: white;
    }
    .firstFooter{
        margin-left: 5rem;
        margin-top: 5rem;
        width: 50%;
    }
    .textFooter{
        margin-top: 1rem;
        width: 70%;
        color: white;
        font-family: 'Outfit';
    }
    footer{
        margin-top: 2rem;
        height: 80vh;
        display: flex;
    }
</style>