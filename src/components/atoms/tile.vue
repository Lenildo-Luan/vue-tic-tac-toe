<template>
    <div class="tile" :class="[state]"></div>
</template>

<script setup>
    defineProps({
        state: String
    })
</script>

<style scoped>
    .tile {
        width: 100%;
        height: 100%;
        background-color: var(--color-background);
    }

    .red {
        background-color: red;
    }

    .green {
        background-color: green;
    }
</style>
  