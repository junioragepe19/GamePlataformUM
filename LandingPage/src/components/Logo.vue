<script setup>

const values = defineProps({
    sizeText: {
        type: String,
        default: ''
    }
})
</script>

<template>
    <div class="iconTitle">
        <p class="titleHeader"  :style="'font-size: ' + values.sizeText">uis<span class="second">mode</span></p>
    </div>
</template>

<style>
.iconTitle{
    margin-top: -0.5rem;
}
.titleHeader{
    color: white;
    font-family: 'a4speed';
}
</style>