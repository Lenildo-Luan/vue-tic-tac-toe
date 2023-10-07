<template>
    <div class="tile-grid">
        <Tile v-for="(tile, index) in tileStates" :key="tile.id" :state="tile.state" @click="changeState(index)"/>
    </div>
</template>

<script setup>
    import { reactive } from 'vue'
    import Tile from '../atoms/tile.vue'

    const props = defineProps({
        player: String
    })

    const emit = defineEmits(['finishGame'])

    const tileStates = reactive([
        { id: 0, state: '' },
        { id: 1, state: '' },
        { id: 2, state: '' },
        { id: 3, state: '' },
        { id: 4, state: '' },
        { id: 5, state: '' },
        { id: 6, state: '' },
        { id: 7, state: '' },
        { id: 8, state: '' }
    ])

    const hasWinning = () => {
        const row1 = tileStates[0].state === props.player && tileStates[1].state === props.player && tileStates[2].state === props.player
        const row2 = tileStates[3].state === props.player && tileStates[4].state === props.player &&  tileStates[5].state === props.player
        const row3 = tileStates[6].state === props.player && tileStates[7].state  === props.player && tileStates[8].state  === props.player
        const column1 = tileStates[0].state === props.player && tileStates[3].state  === props.player && tileStates[6].state === props.player
        const column2 = tileStates[1].state === props.player && tileStates[4].state === props.player && tileStates[7].state === props.player
        const column3 = tileStates[2].state === props.player && tileStates[5].state === props.player && tileStates[8].state === props.player
        const diagonal1 = tileStates[0].state === props.player && tileStates[4].state === props.player && tileStates[8].state === props.player
        const diagonal2 = tileStates[2].state === props.player && tileStates[4].state === props.player && tileStates[6].state === props.player

        return row1 || row2 || row3 || column1 || column2 || column3 || diagonal1 || diagonal2
    }

    const changeState = (index) => {
        tileStates[index].state = props.player
        if(hasWinning()) emit('finishGame')
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
  