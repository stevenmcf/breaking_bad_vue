<template>
  <ul>
      <character-list-item v-for="(character, index) in characters" :character="character" :key="index"></character-list-item>
      
  </ul>
</template>

<script>

import CharacterListItem from './CharacterListItem.vue';

export default {
    name: 'character-list',
    // this needs to match the tags flowing through to the main component
    props: ['characters'],
    components: {
        'character-list-item': CharacterListItem
    },    
}
</script>

<style scoped>

ul {
    list-style: none;
}

</style>