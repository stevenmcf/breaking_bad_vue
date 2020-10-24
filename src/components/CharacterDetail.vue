<template>
  <section class="character-detail">
      <!-- <button v-if="!favouriteCharacters.includes(character)" v-on:click='handleclick' :Value="character">Favourite ?</button> -->
    <h2>Character Details</h2>
    <p>Name: {{ character.name }}</p>
    <p>Goes by: {{ character.nickname }}</p>
    <p>Occupation: {{ character.occupation.toString() }}</p>
    <img :src="character.img" :alt="'Image of' + character.name">
  </section>
</template>

<script>

import { eventBus } from '@/main.js';

export default {
    name: "character-detail",
    props: ['character', 'favouriteCharacters'],

    methods: {
        handleClick () {
            eventbus.$emit('favourite-selected', this.character)
        }
    }
};

</script>

<style scoped>

img {
    height: 80px;
    width: 80px;
    object-fit: contain;
}

</style>