<template>
  <div class="container">
    <Header title="Piterija" />
    <People @person-selected="onPersonSelect" :people="people" />
    <Food @food-selected="onFoodSelect" :food="food" />
    <Button text="Naruči" :disabled="orderButtonDisabled" :person="this.selectedPerson" :food="this.selectedFood"/>
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
      food: [],
      selectedPerson: null,
      selectedFood: [],
    }
  },
  computed: {
    orderButtonDisabled() {
      return !(this.selectedFood.length && this.selectedPerson)
    }
  },
  created() {
    this.people = ['Damjan', 'Davor', 'Dule', 'Ivan', 'Jerko', 'Lovre', 'Nikola', 'Vatro', 'Zvone']
    this.food = ['Jabuka', 'Meso', 'Piletina', 'Sirnica', 'Višnja']
  },
  methods: {
    onPersonSelect(personIndex) {
      this.selectedPerson = this.people[personIndex]
      console.log(this.selectedPerson)
    },
    onFoodSelect(foodIndexes) {
      if (foodIndexes) {
        this.selectedFood = foodIndexes.map(index => this.food[index])
        console.log(this.selectedFood)
      }

    }
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
