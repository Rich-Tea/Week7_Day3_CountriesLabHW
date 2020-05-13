<template lang="html">
  <div v-if='country'>
      <h2>{{ country.name }}</h2>
  </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>

</style>