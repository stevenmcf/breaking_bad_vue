<template>
  <section class="episode-detail">
    <h2>Episode Details</h2>
    <p>Title: {{ episode.title }}</p>
    <p>Season: {{ episode.season }}, episode {{ episode.episode }}</p>
    <p>Main Characters: {{ episode.characters.toString() }}</p>
    
     <!-- <button v-if="!favouriteEpisodes.includes(episode)" v-on:click='handleClick' :Value="episode">Your Favourite ?</button> -->
  </section>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: "episode-detail",
    props: ['episode'],

    // methods: {
    //     handleClick () {
    //         eventBus.$emit('favourite-selected', this.episode)
    //     }
    // },
};

</script>

<style scoped>



</style>