<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersInfo.label }}: </span>
                <span class="value">{{ usersInfo.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    usersInfo: Object
})

</script>