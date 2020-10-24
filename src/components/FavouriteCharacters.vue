<template>
  <section id='favourite-characters'>
      <h3>Your Favourite Characters</h3>
        <ul>
            <li v-for="(favouriteCharacter, index) in favouriteCharacters" :key='index'>Character: {{ favouriteCharacters.name }}
                <br>Nickname: {{favouriteCharacters.nickname }} </br> 
                <img :src="favouriteCharacters.img" :alt="'Image of' + favouriteCharacters.name">
            </li>
        </ul>



  </section>
</template>

<script>
export default {
    name: 'favourite-characters',
    props: ['favouriteCharacters']

}
</script>

<style scoped>



</style>>
