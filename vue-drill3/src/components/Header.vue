<template>
  <div id='page-header'>
    <img src="../assets/g-dino.png">
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
  #page-header {
    grid-row: 1 / 2;
    display: grid;
    grid-template-columns: 25% 50% 15%;
    grid-template-rows: 50% 50%;
    padding-top: 10px;
  }
  img {
    grid-row: 1/3;
    grid-column: 1/2;
    height: 100px;
    width: auto;
  }
</style>
