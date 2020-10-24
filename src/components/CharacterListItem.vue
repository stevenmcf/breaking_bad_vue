<template>
  <li v-on:click='handleClick'>{{ character.name }}</li>
</template>

<script>

import { eventBus } from '@/main.js';
 
export default {
 name: 'character-list-item',
 props: ['character'],
 methods: {
     handleClick() {
            eventBus.$emit('character-selected', this.character)
        }
 }
}

</script>

<style scoped>

li {
display: flex;
align-items: center;
margin: 10px 10px 10px 0;
cursor: pointer;
}

img {
    height: 80px;
    width: 80px;
    object-fit: contain;
}

</style>