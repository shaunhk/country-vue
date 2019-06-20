<template lang="html">

      <option>{{country.name}}</option>

</template>

<script>

import {eventBus} from '../main.js'

export default {
  name: 'country-item',
  props: ['country'],
  methods: {
    selectCountry(){
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
