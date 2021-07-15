<template>
  <div class="container">
    <Header @changeValue="changeAlbum" />
    <Main :albumList="filteredAlbumList"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      albumList:[],
      selectedValue : ''
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.albumList = result.data.response
      this.filteredAlbumList = result.data.response
    })
  },
  computed: {
    filteredAlbumList() {
      return this.albumList.filter ((element) => {
         if (element.genre == this.selectedValue || this.selectedValue == 'All') {
           return true
         } 
      })
    }
  },
  methods: {
    changeAlbum(selected) {
      this.selectedValue = selected
    }
  }
}
</script>

<style lang="scss">
 @import "./style/app.scss"
</style>
