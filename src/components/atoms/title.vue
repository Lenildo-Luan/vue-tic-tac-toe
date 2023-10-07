<template>
    <h2 class="title">{{ props.content }}</h2>
</template>

<script setup>
const props = defineProps({
    content: String
})
</script>

<style scoped>
.title {
    font-size: 2.6rem;
    font-weight: bold;
}
</style>