<template>
  <section id='favourite-characters'>
      <h3>Your Favourite Characters</h3>
        <ul>
            <li v-for="favouriteCharacter in favouriteCharacters" :key='favouriteCharacter'>
                Character: {{ favouriteCharacter.name }}
                <br>Nickname: {{favouriteCharacter.nickname }} </br> 
                <img :src="favouriteCharacter.img" :alt="'Image of' + favouriteCharacter.name">
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
img {
    height: 80px;
    width: 80px;
    object-fit: contain;
}


</style>>
