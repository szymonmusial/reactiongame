<template>
<div class="reaction-block" @click="stopTime" :style="randomPosition()"><span class="reaction-block__text">PRESS ME</span></div>
</template>

<script>
export default {
    name: 'ReactionBlock',
    methods: {
        stopTime() {
            this.$emit('stopTime')
        },
        randomPosition() {
            const position = this.generateRandomNumber(600)
            const style = "margin-left: " + this.generateRandomSign() + position + "px"
            return style
        },
        generateRandomNumber(max) {
            // number bettwen 1 and max + 1
            let number = Math.floor(Math.random() * max) + 1;
            return number
        },
        generateRandomSign() {
            let sign = ""
            if (this.generateRandomNumber(9) > 5) {
                sign = '-'
            }
            return sign
        }
    }
}
</script>

<style scoped>
.reaction-block {
    display: block;
    width: 400px;
    height: 200px;
    background-color: #FB8C00;
    border-radius: 16px;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
