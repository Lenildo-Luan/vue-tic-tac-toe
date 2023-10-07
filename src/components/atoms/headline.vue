<template>
    <h1 class="headline">{{ props.content }}</h1>
</template>

<script setup>
const props = defineProps({
    content: String
})
</script>

<style scoped>
.headline {
    font-size: 4.2rem;
    font-weight: bold;
}
</style>