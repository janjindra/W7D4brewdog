<template lang="html">
<div>
  <h2>Favorite Beers</h2>
  <ul>
     <li v-for="(beer, index) in favoriteBeers" :key="index">{{beer.name}}
     <button v-model="selectedBeer" v-on:click="deleteFave" type="button" name="deleteFave">Remove</button>
   </li>

  </ul>

</div>
</template>

<script>
export default {
  name: "fave-beers",
  data(){
    return {
      selectedBeer: null
    }
  },
  props: ["favoriteBeers"],
methods:{
  deleteFave: function() {
  let beerIndex = this.favoriteBeers.map((beer) => {
      return beer.name
    }).indexOf(selectedBeer.name)
    console.log(beerIndex);
    this.favoriteBeers.splice(beerIndex,1)
  }
}
}
</script>

<style lang="css" scoped>
</style>
