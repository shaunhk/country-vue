<template lang="html">

  <div>
      <select @change="selectCountry" v-model="country">
        <option disabled value="">Select an Operation</option>
        <country-item v-for="(country, index) in countries" :country="country" :key="index"></country-item>
      </select>
  </div>

</template>

<script>
import {eventBus} from '../main.js'
import CountryItem from './CountryItem.vue'

export default {
  name: 'countries-list',
  props: ['countries', 'country-item'],
  // methods: {
  //   selectCountry(){
  //     eventBus.$emit('country-selected', this.country)
  //   },
  },
  components: {
    "country-item": CountryItem
  }
}
</script>

<style lang="css" scoped>
</style>
