<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersInfo.label }}: </span>
                <span v-if="showValue" class="value">{{ usersInfo.value }}</span>
                <span v-if="(completed === true)" class="completed">   Completed</span>
                <span v-else> <Loading /> </span>
            </div>
        </div>
    </div>
</template>

<script setup>
import Loading from '../elements/Loading.vue'
defineProps({
    usersInfo: Object,
    showValue: Boolean,
    completed: Boolean
})
</script>