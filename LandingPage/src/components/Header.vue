<script setup>
import Logo from './Logo.vue';

</script>

<template>
    <header class="d-flex header">
        <logo sizeText="1.8rem" />
        <nav class="d-flex gap-2 text-white text-">
            <a>tournaments</a>
            <a>Ladder</a>
            <a>Shop</a>
            <a>Community</a>
            <a>Stream</a>
        </nav>
        <div class="account">
            Alguma coisa
        </div>
    </header>
</template>


<style>
@import '../app.scss';
.account{
    color: white;
}
nav{
    font-family: 'Outfit';
    gap: 2.5rem;
}

.second{
    color: #bef970;
}
.header{
    z-index: 999;
    align-items: start;
    position: relative;
    margin-top: 1rem;
    font-size: 1.2rem;
    width: 100%;
    height: 20%;
    justify-content:space-around;
}
</style>