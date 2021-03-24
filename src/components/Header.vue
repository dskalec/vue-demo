<template>
  <header>
    <div>
      <img :alt="title" src="../assets/oklagija.png">
      <h1>{{ title }}</h1>
    </div>
  </header>
</template>

<script>

  export default {
    name: 'Header',
    props: {   // define props as an object
      title: {
        type: String,
        default: 'Oklagija'
      }
    }
  }
</script>

<style scoped>
  h1 {
    text-align: center;
    margin: auto;
    position: relative;
    vertical-align: middle;
  }
  img {
    float: left;
  }
  div {
    display: flex;
    margin-bottom: 50px;
  }
</style>