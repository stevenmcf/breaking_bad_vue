<template>
  <ul>
      <character-list-item v-for="(character, index) in characters" :key="character" :character="character"></character-list-item>
      
  </ul>
</template>

<script>

import CharacterListItem from './CharacterListItem.vue';

export default {
    name: 'character-list',
    // this needs to match the tags flowing through to the main component
    components: {
        'character-list-item': CharacterListItem
    },

    props: ['characters'],
    
}
</script>

<style>

</style>