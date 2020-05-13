<template lang="html">
  <div>
      <ul>
          <country-list-item v-for="(country, index) in countries" :country="country" :key="index"></country-list-item>
      </ul>
  </div>
</template>

<script>
import CountryListItem from './ListComponent.vue';

export default {
    name: 'countries-list',
    props: ['countries'],
    components: {
      "country-list-item": CountryListItem
    }
}
</script>

<style>

</style>