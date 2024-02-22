<template>
    <span class="frame">{{ frame }}</span>
</template>

<script setup>
import { ref } from 'vue';

let frames = ['loading', 'loading.', 'loading..', 'loading...'];
let frame = ref(frames[0]);

let i = 0;
setInterval(() => {
    frame.value = frames[i++ % frames.length];
}, 200)
</script>

<style scoped>
.frame {
    font-family: 'Terminus', monospace;
    font-size: 13px;
}
</style>