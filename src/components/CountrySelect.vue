<template lang="html">
  <div>
      <select @change="selectCountry()">
        <option disabled value="">Select an Operation</option>
        <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
      </select>
  </div>
</template>

<script>

import {eventBus} from '../main.js'

export default {
  name: 'country-select',
  props: ['countries', 'country'],
  methods: {
    selectCountry(){
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
