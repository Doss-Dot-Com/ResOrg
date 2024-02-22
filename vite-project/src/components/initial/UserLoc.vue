<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersLoc.label }}: </span>
                <span v-if="showValue" class="value">{{ usersLoc.value }}</span> 
                <span v-if="(completed === true)" class="completed">   Completed</span>
                <span v-else> <Loading /> </span>
            </div>
        </div>
    </div>
</template>

<script setup>
import Loading from '../elements/Loading.vue'

defineProps({
    usersLoc: Object,
    showValue: Boolean,
    completed: Boolean

})
</script>
