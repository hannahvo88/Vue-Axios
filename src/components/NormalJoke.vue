<template>
    <div>
        <button id="normalButton" @click="normalJoke">How normal this joke is!</button>
    </div>
</template>

<script>
    export default {
        name : "NormalJoke",
        methods: {
            normalJoke() {
                return this.$store.commit('normalJoke');
            }
        }
    }
</script>

<style scoped>
    #normalButton {
        background-color: brown;
        border: black solid 1px;
    }
</style>