<template>
    <div>

        <h1>{{selectedJoke()}}</h1>
        <button id="button" @click="requestJoke">Let's try to find some new Jokes</button>
    </div>
</template>

<script>
import axios from 'axios'

    export default {
        name : "JokeButton",
        methods: {
            requestJoke() {
                axios.request({
                    url: "https://geek-jokes.sameerkumar.website/api?format=json",
                    method: "GET"
                }).then((response) => {
                    console.log(response.data.joke);
                    return this.$store.commit("requestedJoke", response.data.joke);
                    
                })
            },
            selectedJoke() {
                if(this.$store.state.theJoke !== "") {
                    return this.$store.state.theJoke
                } else {
                    return this.$store.state.getAJoke
                }
            },
        }
    }
</script>