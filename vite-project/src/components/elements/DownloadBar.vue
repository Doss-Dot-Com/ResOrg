<template>
    <span> Downloading: [ {{ progress }} {{ num * steps }}% ] </span>
</template>

<script setup>
import { ref } from 'vue';

const char = '▆'
const min = 0;
const max = 100;
const steps = 5;
let num = ref(0);
let progress = ref('')

const mInterval = setInterval (() => {
    progress.value = '';
    for (let i = 0; i < num.value; i++) {
        progress.value += char;
    }
    num.value++
    if (num.value >= max / steps) {
        clearInterval(mInterval)
    }   
}, 100)
</script>

<style scoped>
span {
    font-family: 'Terminus', monospace;
    font-size: 12px;}
</style>