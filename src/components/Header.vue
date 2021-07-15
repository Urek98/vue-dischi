<template>
  <div class="header-section flex">
    <img class="logo" src="../assets/spotify-logo.png" alt="" />
    <div>
      <select v-model="selected" @change="$emit('changeValue',selected)">
        <option>All</option>
        <option>Rock</option>
        <option>Pop</option>
        <option>Jazz</option>
        <option>Metal</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data(){
    return {
      selected : ""
    }
  }
};
</script>


<style scoped lang="scss">
.header-section {
  height: 70px;
  background-color: rgb(46, 58, 70);
  padding: 10px;
  align-items: center;
  justify-content: space-between;
  .logo {
    height: 100%;
  }
  select{
    background-color: rgb(46, 58, 70);
    color: whitesmoke;
    width: 100px;
    font-size: 20px;
    border: 2px solid white;
    border-radius: 5px;
  }
}
</style>
