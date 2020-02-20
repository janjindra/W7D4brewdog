<template lang="html">
<div>
<beer-list :beers="beers"> </beer-list>
<beer-detail :beer="selectedBeer" v-if="selectedBeer"/>

</div>
</template>

<script>
import BeerList from './components/BeerList.vue';
import BeerDetail from './components/BeerDetails.vue';
import {eventBus} from './main.js';

export default {
  name: 'app',
  data () {
    return {
      beers: [],
      selectedBeer: null
    };
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer;
    })

  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail
  }
}
</script>

<style lang="css" scoped>
</style>
