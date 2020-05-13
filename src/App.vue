<template>
  <div id="app">
    <h1>List of countries</h1>
    <div class="main-container"></div>
    
    <countries-list :countries="countries"></countries-list>
    <country-detail :countries="selectedCountry"></country-detail>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import CountryListItem from './components/ListComponent.vue';

export default {
  name: 'App',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
     fetch('https://restcountries.eu/rest/v2/all')
     .then(res => res.json())
     .then(countries => this.countries = countries)

     eventBus.$on('country-selected', (country) => {
       this.selectedCountry = country
     })
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
    
  }
}
</script>

<style>
.main-container {
    display: flex;
    justify-content: space-between;
  }

</style>
