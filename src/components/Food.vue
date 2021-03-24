<template>
  <div id="food">
    <h3>Pita:</h3>
    <Multiselect
      v-model="selectedFood"
      v-bind:options="food"
      :searchable="true"
      mode="tags"
      placeholder="Odaberi pitu..."
      :select="onSelect(selectedFood)"
    />
  </div>
</template>

<script>
  import Multiselect from '@vueform/multiselect'

  export default {
    name: 'Food',
    components: {
      Multiselect
    },
    props: {
      food: Array
    },
    data() {
      return {
        selectedFood: null,
      }
    },
    methods: {
      onSelect(value) {
        console.log(value)
      }
    }
  }
</script>

<style src="@vueform/multiselect/themes/default.css">
  #food {
    margin-top: 40px;
    margin-bottom: 40px;
  }
</style>