<template>
  <div id="food">
    <h3>Odabir hrane:</h3>
    <Multiselect
      v-model="selectedFood"
      v-bind:options="food"
      :searchable="true"
      mode="tags"
      placeholder="Odaberi pitu..."
      :select="onSelect()"
      ref="multiselect"
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
      onSelect() {
        this.$emit('food-selected', this.selectedFood)
      },
      resetSelection() {
        this.$refs.multiselect.clear()
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