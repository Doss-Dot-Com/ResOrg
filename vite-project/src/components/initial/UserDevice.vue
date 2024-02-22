<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersDevice.label }}: </span>
                <span v-if="showUserDevice" class="value">{{ usersDevice.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
    usersDevice: Object
})

const showUserDevice = ref(false)

onMounted (() => {
    setTimeout(() => {
        showUserDevice.value = true;
    }, 2000)
})
</script>