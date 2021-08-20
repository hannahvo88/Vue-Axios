<template>
    <div>
        <button id="loudButton" @click="loudJoke">It will be really loud!</button>
    </div>
</template>

<script>
    export default {
        name : "LoudJoke",
        computed: {
            requestLoudJoke() {
                return this.$store.getters.makeJokeLoud;
            },
            methods: {
                loudJoke() {
                return this.$store.commit("loudJoke", this.getLoudJoke);
            }
        },
    }}
</script>

<style scoped>
    #loudButton {
        background-color: aqua;
        border: black solid 1px;
    }
</style>