<template>
    <h3 class="subtitle">{{ props.content }}</h3>
</template>

<script setup>
const props = defineProps({
    content: String
})
</script>

<style scoped>
.subtitle {
    font-size: 1.6rem;
}
</style>