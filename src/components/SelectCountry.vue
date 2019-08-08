<template lang="html">
  <select v-on:change="handleChange" v-model="selectedCountry">
    <option v-for="country in countries" :value="country">{{country.name}}</option>

  </select>

</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: "select-country",
  data(){
    return {
      "selectedCountry": {},
    }
  },
  props: ["countries"],
  methods: {
  handleChange(){
    eventBus.$emit('country-selected', this.selectedCountry);
  }
}
}
</script>

<style lang="css" scoped>

</style>
