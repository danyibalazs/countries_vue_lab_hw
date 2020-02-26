<template lang="html">
  <ul>
    <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
  </ul>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
