<template>
  <div class="main-section flex">
    <Album v-for="album in albumList" :key='album.index'
    :poster='album.poster'
    :title='album.title'
    :author='album.author'
    :year='album.year'/>
  </div>
</template>

<script>
import Album from './Album.vue'

export default {
  name: "Main",
  components:{
      Album,
  },
  props: {
      albumList: Array
  }
};
</script>


<style scoped lang="scss">
    .main-section{
        background-color: rgb(30,45,59);
        padding: 30px 0;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>
