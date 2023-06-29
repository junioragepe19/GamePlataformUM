<template>
    <header class="d-flex header">
        <div class="iconTitle">
            <p class="titleHeader">uis<span class="second">mode</span></p>
        </div>
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
.titleHeader{
    font-size: 1.5rem;
    color: white;
    font-family: 'a4speed';
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