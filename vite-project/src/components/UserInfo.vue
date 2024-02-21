<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ userInfo.label }}</span>: <!-- Updated -->
                <span class="value typingEffect">{{ userInfo.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    userInfo: Object
})

</script>
