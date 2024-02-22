<template>
    <div>
        <div class="grid-container">
            <div class="info-item">
                <span class="label">{{ usersInfo.label }}: </span>
                <span v-if="showInfoValue" class="value">{{ usersInfo.value }}</span> 
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
    usersInfo: Object
})

const showInfoValue = ref(false)

onMounted(() => {
    setTimeout(() => {
        showInfoValue.value = true
    }, 1000)
})

</script>