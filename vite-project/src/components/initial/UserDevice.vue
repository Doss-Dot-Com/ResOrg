<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersDevice.label }}: </span>
                <span class="value">{{ usersDevice.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    usersDevice: Object
})

</script>