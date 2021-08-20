<template>
    <div>
         <button id="snakeButton" @click="snakeJoke">It is the Snake Joke</button>
        
    </div>
</template>

<script>
    export default {
        name : "SnakeJoke",
        computed: {
            requestSnakeJoke() {
                return this.$store.getters.makeJokeSnake;
            }
        },
        methods: {
            snakeJoke() {
                return this.$store.commit("snakeJoke", this.getSnakeJoke);
            }
        }}
</script>

<style scoped>
    #snakeButton {
        background-color: blanchedalmond;
        border: black solid 1px;
    }
</style>