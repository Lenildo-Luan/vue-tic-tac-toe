<template>
    <div class="tile-grid">
        <Tile v-for="(tile, index) in tileStates" :key="tile.id" :state="tile.state" @click="changeState(index)"/>
    </div>
</template>

<script setup>
    import { reactive } from 'vue'
    import Tile from '../atoms/tile.vue'
    
    const props = defineProps({
        player: Number
    })

    const tileStates = reactive([
        { id: 0, state: -1 },
        { id: 1, state: -1 },
        { id: 2, state: -1 },
        { id: 3, state: -1 },
        { id: 4, state: -1 },
        { id: 5, state: -1 },
        { id: 6, state: -1 },
        { id: 7, state: -1 },
        { id: 8, state: -1 }
    ])

    const changeState = (index) => {
        console.log(tileStates)
        tileStates[index].state = props.player
    }
</script>

<style scoped>
    .tile-grid {
        height: 390px;
        width: 390px;

        display: grid;
        grid-template-columns:  repeat(3, 1fr);
        background-color: var(--color-border);
        border: var(--color-border) solid 0.1rem;
        gap: 0.1rem;
    }
</style>
  