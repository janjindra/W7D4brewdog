<template lang="html">
<div>
  <ul>
  <beer-item  v-for="(beer, index) in beers" :key="index" :beer="beer"> </beer-item>
</ul>
</div>
</template>


<script>

import BeerItem from './BeerItem.vue';

export default {
  name: 'beer-list',
  props: ["beers"],
  components: {
    "beer-item": BeerItem
  }
}
</script>

<style lang="css" scoped>
</style>
