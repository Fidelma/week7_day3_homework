<template lang="html">
  <div>
    <ul>
      <list-item v-for="(country, index) in countries" :key="index" :country="country" ></list-item>
    </ul>
  </div>

</template>

<script>

import ListItem from './ListComponent.vue'

export default {
  name: 'countries-list',
  props: ["countries"],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
