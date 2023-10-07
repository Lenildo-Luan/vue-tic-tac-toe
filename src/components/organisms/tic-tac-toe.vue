<template>
    <div class="tic-tac-toe">
        <Title content="Tic-Tac-Toe"/>
        <CtaBanner v-if="winner" />
        <Subtitle v-else :content="`Player's ${currentPlayer} turn`"/>
        <TileGrid :player="player" @click="changePlayer" @finish-game="finishGame"/>
    </div>
</template>

<script setup>
    import { ref, computed } from 'vue'
    import Title from '../atoms/title.vue'
    import Subtitle from '../atoms/subtitle.vue'
    import CtaBanner from '../molecules/cta-banner.vue'
    import TileGrid from '../molecules/tile-grid.vue'

    const player = ref(0)
    const winner = ref('')

    const changePlayer = () => player.value == 0 ? player.value = 1 : player.value = 0
    const finishGame = () => winner.value = player.value

    const currentPlayer = computed(() => player.value ? 'GREEN' : 'RED')
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
  