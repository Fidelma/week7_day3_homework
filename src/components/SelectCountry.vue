<template lang="html">
  <select v-on:change="handleChange">
    <option v-for="(country, index) in countries" :selectedCountry="country" >{{country.name}}</option>

  </select>

</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: "select-country",
  props: ["countries"],
  methods: {
  handleChange(){
    eventBus.$emit('country-selected', this.country);
  }
}
}
</script>

<style lang="css" scoped>
</style>
