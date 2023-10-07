<template>
    <div class="tic-tac-toe">
        <Title content="Tic-Tac-Toe"/>
        <CtaBanner v-if="winner" />
        <Subtitle v-else :content="`Player's ${player.toUpperCase()} turn`"/>
        <TileGrid :player="player" @click="changePlayer" @finish-game="finishGame"/>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    import Title from '../atoms/title.vue'
    import Subtitle from '../atoms/subtitle.vue'
    import CtaBanner from '../molecules/cta-banner.vue'
    import TileGrid from '../molecules/tile-grid.vue'

    const player = ref('red')
    const winner = ref('')

    const changePlayer = () => player.value === 'red' ? player.value = 'green' : player.value = 'red'
    const finishGame = () => winner.value = player.value
</script>

<style scoped>
    .tic-tac-toe {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .tic-tac-toe > .cta-banner,
    .tic-tac-toe > .subtitle {
        margin-bottom: 2rem;
    }
</style>
  