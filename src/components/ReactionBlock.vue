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
            const position = this.generateRandomNumber()
            const style = "margin-left: " + position +"px"
            console.log(style)
            return style
        },
        generateRandomNumber() {
            // number bettwen 1 and 601
            let number = Math.floor(Math.random() * 600) + 1;
            return number
        },
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
