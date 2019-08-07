<template lang="html">
  <div v-if="selectedCountry">
    <h3>{{selectedCountry.name}}</h3>

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
