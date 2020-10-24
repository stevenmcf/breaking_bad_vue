<template>
  <ul>
      <li>List of episodes</li>
  </ul>
</template>

<script>
export default {
    name: "episode-list",
    props: ['episodes'],
    // components: {
    //     EpisodeListItem
    // }
}

</script>

<style>
ul {
    list-style: none;
}
</style>