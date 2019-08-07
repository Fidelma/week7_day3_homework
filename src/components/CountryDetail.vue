<template lang="html">
  <div v-if="selectedCountry">
    <h3>{{selectedCountry.name}}</h3>
    <p>Capital: {{selectedCountry.capital}}</p>
    <p>Population: {{selectedCountry.population}}</p>

  </div>

</template>

<script>
export default {
  name: 'country-detail',
  props: ['selectedCountry']
}
</script>

<style lang="css" scoped>
</style>
