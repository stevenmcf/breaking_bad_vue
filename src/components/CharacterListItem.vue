<template>
  <li v-on:click='handleClick'>
    <img :src="character.img" alt="Image of 'character.name'"/>
        <span>Name: {{ character.name }}</span>
        <span>Nickname: {{ character.nickname }}</span>
    </li>
</template>

<script>

import { eventBus } from '@/main.js';
 
export default {
 name: 'character-list-item',
 props: ['character'],
 methods: {
     handleClick (){
        //  emit from eventbus
        eventBus.$emit('character-selected', this.character);
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