<template lang='html'>
<main id="app">
  <h1>BreakingBad(code)</h1>
  <!-- <character-list :characters="characters"> </character-list> -->
    <label for="selected_character">Select a Character</label>
      <select id="selected_character" v-model="selectedCharacter">
          <option disabled value="">Select a character</option>
          <option v-for="(character, index) in characters" :character="character" :key="index" :value="character">{{ character.name}} </option>
      </select>
  
    <character-detail v-if="selectedCharacter":character="selectedCharacter" :favouriteCharacters='favouriteCharacters'></character-detail>

    <favourite-characters :favouriteCharacters='favouriteCharacters'></favourite-characters>

</main>
  
</template>

<script>

import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue'
import FavouriteCharacters from './components/FavouriteCharacters.vue'
import EpisodeList from './components/EpisodeList.vue'
import { eventBus } from '@/main.js'

export default {
  name: 'app', 
  data () {
    return {
      characters: [],
      selectedCharacter: null,
      favouriteCharacters: [],
      episodes: [],
      selectedEpisode: null
    }
  },

// once child component added, component needs to be confirmed in parent.
  components: {
    'character-list': CharacterList,
    'character-detail': CharacterDetail,
    'favourite-characters': FavouriteCharacters,
    'episode-list': EpisodeList,
    // 'episode-detail': EpisodeDetail
  },


// Use mounted to grab the data before app loads. 
  mounted() {
    // character fetch list
    fetch('https://www.breakingbadapi.com/api/characters')
      .then(res => res.json())
      .then(characters => this.characters = characters)


    // episode fetch list
    fetch('https://www.breakingbadapi.com/api/episodes')
      .then(res => res.json())
      .then(episodes => this.episodes = episodes)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })

    eventBus.$on('favourite-selected', (character) => {
      this.favouriteCharacters.unshift(character)
    })

  },

  // methods: {
  //   addToFavourites: function() {
  //     this.favouriteCharacters.push
  //   }
  // }

}
</script>

<style lang='css' scoped>




</style>