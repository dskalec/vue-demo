<template>
  <div id="people">
    <h3>Osoba:</h3>
    <Multiselect
      v-model="selectedPerson"
      :options="people"
      placeholder="Tko naručuje?"
      :searchable="true"
      @select="onSelect(this.selectedPerson)"
      @deselect="onSelect(null)"
      ref="multiselect"
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
      onSelect(selectedPersonIndex) {
        this.$emit('person-selected', selectedPersonIndex)
      },
      resetSelection() {
        this.$refs.multiselect.clear()
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