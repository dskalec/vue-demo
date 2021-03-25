<template>
  <div class="container">
    <Header title="Piterija" />
    <People @person-selected="onPersonSelect" :people="people" ref="people" />
    <Food @food-selected="onFoodSelect" :food="food" ref="food" />
    <Button
        text="Naruči"
        :disabled="orderButtonDisabled"
        :person="this.selectedPerson"
        :food="this.selectedFood"
        @order-placed="onOrderPlacement"
    />
    <Orders :orders="orders"/>
  </div>
</template>

<script>
import {v4 as uuidv4} from 'uuid'

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
      orders: []
    }
  },
  computed: {
    orderButtonDisabled() {
      return !(this.selectedFood.length && this.selectedPerson)
    },
  },
  created() {
    this.people = ['Damjan', 'Davor', 'Dule', 'Ivan', 'Jerko', 'Lovre', 'Nikola', 'Vatro', 'Zvone']
    this.food = ['Jabuka', 'Meso', 'Piletina', 'Sirnica', 'Višnja']
  },
  methods: {
    onPersonSelect(personIndex) {
      this.selectedPerson = this.people[personIndex]
    },
    onFoodSelect(foodIndexes) {
      if (foodIndexes) {
        this.selectedFood = foodIndexes.map(index => this.food[index])
      }
    },
    resetValues() {
      this.$refs.food.resetSelection()
      this.$refs.people.resetSelection()
    },
    onOrderPlacement(person, food) {
     this.orders.push({
        id: uuidv4(),
        name: person,
        food: food,
        orderTime: new Date().toLocaleString()
      })
     this.resetValues()
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
