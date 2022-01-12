<template>
<div class="game">

    <start-game @startGame="startGame"></start-game>
    <reaction-block></reaction-block>

</div>
</template>

<script>
import StartGame from './components/StartGame.vue'
import ReactionBlock from './components/ReactionBlock.vue'

export default {
    name: 'App',
    components: {
        StartGame,
        ReactionBlock
    },
    methods: {
        startGame() {
        console.log("start game")
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.game {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 160px;
}
</style>
