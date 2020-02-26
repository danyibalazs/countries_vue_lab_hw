<template lang="html">
  <select>
    <option @change="handleChange" v-for="(country, index) in countries">{{country.name}}</option>
  </select>
</template>

<script>

export default {
  name: 'country-select',
  props: ['countries'],
  components: {

  },
  methods: {
    handleChange(){
      console.log(countries);
      eventBus.$emit('country-changed', this.countries[index])

    }
  }
}
</script>

<style lang="css" scoped>
</style>
