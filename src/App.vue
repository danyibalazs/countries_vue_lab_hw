<template>
  <div id="app">
    <h1>Countries:</h1>
    <countries-list :countries='countries'></countries-list>
    <country-details :country='selectedCountry'></country-details>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js';

export default {
  name: 'App',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(data => this.countries = data)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "countries-list": CountriesList,
    "country-details": CountryDetail
  }
}
</script>

<style>
#app {

  display: flex;

}
</style>
