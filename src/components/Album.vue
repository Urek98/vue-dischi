<template>
  <div class="album-card">
    <img class="album-img" :src="poster" alt="poster" />
    <h2>{{ title }}</h2>
    <div class="author">{{ author }}</div>
    <div>{{ year }}</div>
  </div>
</template>

<script>
export default {
  name: "Album",
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>


<style scoped lang="scss">
.album-card {
  width: 150px;
  height: 300px;
  background-color: rgb(46, 58, 70);
  text-align: center;
  margin: 20px 40px;
  .album-img {
    width: 100%;
    padding: 20px;
  }
  h2 {
    color: white;
  }
  div{
      color: rgb(128,109,93);
  }
  .author{
      padding-top: 10px;
  }
}
</style>
