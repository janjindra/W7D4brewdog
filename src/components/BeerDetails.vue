<template lang="html">
  <section v-if="beer">
  <h3>Name: {{beer.name}}</h3>
  <p>Tag Line: {{beer.tagline}}</p>
  <img :src="beer.image_url" height="400" width="100"/>
  <p class="wrap">Brewers Tips: {{beer.brewers_tips}}</p>

<div v-if="!favoriteBeers.includes(beer)">
  <button v-on:click="addFavorite" type="button" name="favorite">Add to Favorites</button>
</div>

  <fave-beers :favoriteBeers="favoriteBeers"/>

  </section>
</template>

<script>
import FaveBeers from './FaveBeers.vue'

export default {
  name: 'beer-detail',
  props: ['beer'],
  data () {
    return {
      favoriteBeers: []
    }
  },
  methods: {
    addFavorite: function(){
      this.favoriteBeers.push(this.beer)
    }
  },
  components: {
    "fave-beers": FaveBeers
  }
}
</script>

<style lang="css" scoped>

</style>
