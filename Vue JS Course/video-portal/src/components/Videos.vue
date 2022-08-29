<template>
  <ul>
     <Item v-for="video in videos" v-bind:key="video.id" v-bind:video="video"> 
     </Item>
  </ul>
</template>

<script>
import Item from "./Item.vue";

export default {
name: 'Videos',
components:{
    Item
},
props:{
    videos: Array
    }
}
</script>

<style>

</style>