<template>
  <section class="character-detail">
    <h2>Character Details</h2>
    <p>Name: {{ character.name }}</p>
    <p>Goes by: {{ character.nickname }}</p>
    <p>Occupation: {{ character.occupation.toString() }}</p>
    <img :src="character.img" :alt="'Image of' + character.name">
     <button v-if="!favouriteCharacters.includes(character)" v-on:click='handleClick' :Value="character">Your Favourite ?</button>
  </section>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: "character-detail",
    props: ['character', 'favouriteCharacters'],

    methods: {
        handleClick () {
            eventBus.$emit('favourite-selected', this.character)
        }
    },
};

</script>

<style scoped>

img {
    height: 80px;
    width: 80px;
    object-fit: contain;
}

</style>