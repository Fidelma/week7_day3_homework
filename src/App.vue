<template>
  <div id="app">
    <h1>Countries</h1>
    <div class="main-container">

    <!-- <countries-list :countries='countries'></countries-list> -->
    <select-country :countries='countries'></select-country>
    <country-detail :selectedCountry='selectedCountry'></country-detail>

  </div>

  </div>
</template>

<script>
import {eventBus} from './main.js';
// import CountriesList from './components/CountriesList.vue';
import SelectCountry from './components/SelectCountry.vue'
import CountryDetail from './components/CountryDetail.vue';


export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })


  },
  components: {
    // "countries-list": CountriesList,
    "select-country": SelectCountry,
    "country-detail": CountryDetail
  }
}
</script>

<style>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
