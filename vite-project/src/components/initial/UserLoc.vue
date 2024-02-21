<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersLoc.label }}: </span>
                <span class="value">{{ usersLoc.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    usersLoc: Object
})

</script>
