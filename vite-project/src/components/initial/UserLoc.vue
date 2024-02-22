<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersLoc.label }}: </span>
                <span v-if="showValue" class="value">{{ usersLoc.value }}</span> 
                <span v-if="(completed === true)" class="completed">   Completed</span>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    usersLoc: Object,
    showValue: Boolean,
    completed: Boolean

})
</script>
