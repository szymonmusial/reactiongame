<template>
<div class="game">
    <header-text :reactionTime="reactionTime"/>
    <start-game @startGame="startGame" :disabled="game.status"/>
    <reaction-block v-if="game.status" @stopTime="stopTime"/>
</div>
</template>

<script>
import StartGame from './components/StartGame.vue'
import ReactionBlock from './components/ReactionBlock.vue'
import HeaderText from './components/HeaderText.vue'

export default {
    name: 'App',
    components: {
        StartGame,
        ReactionBlock,
        HeaderText
    },
    data() {
        return {
            game: {
                timeStart: 0,
                timeStop: 0,
                status: false
            }
        }
    },
    methods: {
        startGame() {
            const delay = this.generateRandomTime()
            setTimeout(this.showReactionBlock, delay)
        },
        showReactionBlock() {
            this.game.status = true
            this.game.timeStart = this.getCurrentTime()
            console.log("game start!")
        },
        generateRandomTime() {
            // time bettwen 1 and 4
            let time = Math.floor(Math.random() * 3) + 1;
            time = time * 1000
            return time
        },
        getCurrentTime() {
            const time = new Date()
            return time.getTime()
        },
        stopTime() {
            this.game.status = false
            this.game.timeStop = this.getCurrentTime()
        },
        reactionTime() {
            let result = this.game.timeStop - this.game.timeStart
            return result
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
    gap: 100px;
}
</style>
