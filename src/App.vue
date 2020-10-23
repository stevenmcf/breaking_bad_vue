<template lang='html'>
<main id="app">
  <h1>Breaking Bad</h1>
</main>
  
</template>

<script>
export default {
  // name: 'app', 
  // data () {
  //   return {
  //     characters: [],
  //     selectedCharacters: null,
  //     favouriteCharacters: [],
  //     episodes: [],
  //     selectedEpisode: null, 
  //   }
  // },

  // components: {
  //   'character-list': CharacterList,
  //   'character-detail': CharacterDetail,
  //   'favourite-character': FavouriteCharacter,
  //   'episode-list': EpisodeList,
  //   'episode-detail': EpisodeDetail
  // },

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