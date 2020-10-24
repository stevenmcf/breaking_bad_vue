<template>
  <section class="character-detail">
    <h2>Character Details</h2>
    <p>Name: {{ character.name }}</p>
    <p>Goes by: {{ character.nickname }}</p>
    <p>Occupation: {{ character.occupation }}</p>
    <img :src="character.img" :alt="'Image of' + character.name">
  </section>
</template>

<script>

export default {
    name: "character-detail",
    props: ['character'],
};

</script>

<style scoped>

img {
    height: 80px;
    width: 80px;
    object-fit: contain;
}

</style>