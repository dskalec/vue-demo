<template>
  <div id="people">
    <h3>Osoba:</h3>
    <Multiselect
      v-model="selectedPerson"
      :options="people"
      placeholder="Tko naručuje?"
      :searchable="true"
      @select="onSelect()"
    />
  </div>
</template>

<script>
  import Multiselect from '@vueform/multiselect'

  export default {
    name: 'People',
    components: {
      Multiselect
    },
    props: {
      people: Array
    },
    data() {
      return {
        selectedPerson: null,
      }
    },
    methods: {
      onSelect() {
        this.$emit('person-selected', this.selectedPerson)
      }
    }
  }
</script>

<style src="@vueform/multiselect/themes/default.css">
  #people {
    margin-top: 40px;
    margin-bottom: 40px;
  }
</style>