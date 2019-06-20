<template>
  <div id="app">
    <h1>Countries of the World</h1>
      <div class="main-container">
        <country-select :countries='countries'></country-select>
        <country-detail :country='selectedCountry'></country-detail>
      </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import CountryDetail from './components/CountryDetail.vue';
import CountrySelect from './components/CountrySelect.vue'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  components: {
    "country-select": CountrySelect,
    "country-detail": CountryDetail
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.countries = data);
    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
