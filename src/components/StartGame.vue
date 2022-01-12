<template>
<button class="start-game" @click="startGame"> START THE GAME</button>
</template>

<script>
export default {
    name: 'StartGame',
    methods: {
    startGame() {
    this.$emit('startGame')
    }
    }
}
</script>

<style scoped>
.start-game {
    padding: 16px 24px;
    border-radius: 8px;
    border: 0px;
    background-color: #1565C0;
    color: #fff;
    font-weight: 600;
}
</style>
