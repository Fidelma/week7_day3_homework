<template lang="html">
  <select v-on:change="handleChange" v-model="country">
    <option v-for="(country, index) in countries" :country="country">{{country.name}}</option>

  </select>

</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: "select-country",
  props: ["countries"],
  methods: {
  handleChange(){
    console.log(this);
    eventBus.$emit('country-selected', this.country);
  }
}
}
</script>

<style lang="css" scoped>
</style>
