<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersDevice.label }}: </span>
                <span v-if="showValue" class="value">{{ usersDevice.value }}</span>
                <span v-if="(completed === true)" class="completed">   Completed</span>
                <span v-else> <DownloadBar /></span>
            </div>
        </div>
    </div>
</template>

<script setup>
import DownloadBar from '../elements/DownloadBar.vue'

defineProps({
    usersDevice: Object,
    showValue: Boolean,
    completed: Boolean,
})
</script>