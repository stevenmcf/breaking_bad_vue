<template lang='html'>
<main id="app">
  <character-list :characters="characters"> </character-list>
</main>
  
</template>

<script>

import CharacterList from './components/CharacterList.vue'

export default {
  name: 'app', 
  data () {
    return {
      characters: [],
      // selectedCharacters: null,
      // favouriteCharacters: [],
      episodes: [],
      // selectedEpisode: null, 
    }
  },

// once child component added, component needs to be confirmed in parent.
  components: {
    'character-list': CharacterList,
  //   'character-detail': CharacterDetail,
  //   'favourite-character': FavouriteCharacter,
  //   'episode-list': EpisodeList,
  //   'episode-detail': EpisodeDetail
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
  },

}
</script>

<style lang='css' scoped>




</style>