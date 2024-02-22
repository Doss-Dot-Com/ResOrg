<template>
    <span>Obtaining more data...  {{ frame }}</span>
</template>

<script setup>
import { ref } from 'vue';

let frames = ['/', '-', '\\', '|'];
let frame = ref(frames[0]);

let i = 0;
setInterval(() => {
    frame.value = frames[i++ % frames.length];
}, 200);
</script>

<style scoped>
span {
    font-family: 'Terminus', monospace;
    font-size: 13px;
}
</style>