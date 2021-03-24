<template>
  <div class="container">
    <Header title="Piterija" />
    <People :people="people" />
    <Food :food="food" />
    <Button text="Naruči"/>
    <Orders />
  </div>
</template>

<script>
import Header from './components/Header'
import Orders from './components/Orders'
import People from './components/People'
import Food from './components/Food'
import Button from './components/Button'

export default {
  name: 'App',
  components: {
    Button,
    Food,
    Header,
    Orders,
    People,
  },
  data () {
    return {
      people: [],
      food: []
    }
  },
  created() {
    this.people = ['Damjan', 'Davor', 'Dule', 'Ivan', 'Jerko', 'Lovre', 'Nikola', 'Vatro', 'Zvone']
    this.food = ['Jabuka', 'Meso', 'Piletina', 'Sirnica', 'Višnja']
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 1024px;
  margin: 30px auto;
  overflow: auto;
}
</style>
