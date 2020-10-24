<template>
  <section id='favourite-characters'>
      <h3>Your Favourite Characters</h3>
        <ul>
            <li v-for="favouriteCharacter in favouriteCharacters">Character: {{ favouriteCharacter.name }}
                <br>Nickname: {{favouriteCharacter.nickname }} </br> 
                <img :src="favouriteCharacter.img" :alt="'Image of' + favouriteCharacter.name">
            </li>
        </ul>



  </section>
</template>

<script>
export default {
    name: 'favourite-characters',
    props: ['favouriteCharacter']

}
</script>

<style scoped>



</style>>
