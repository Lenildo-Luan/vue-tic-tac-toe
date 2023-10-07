<template>
    <div class="cta-banner">
        <Headline content="Player RED wins!" />
        <Button content="New Game" />
    </div>
</template>

<script setup>
    import Headline from '../atoms/headline.vue'
    import Button from '../atoms/button.vue'
</script>

<style scoped>
    .cta-banner {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
  