<template lang="html">
  <div>
    <ul>
      <li v-on:click="handleClick">{{country.name}}</li>
    </ul>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'country-item',
  props: ['country'],
  methods: {
    handleClick(){
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
