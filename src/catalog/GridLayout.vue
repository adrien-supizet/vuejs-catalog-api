<template lang="html">
  <b-container id="myGrid" class="bv-example-row">
    <b-row>
        <b-col class sm="3" md="2" v-for='hero in heroes' v-if='!hero.thumbnail.path.includes("image_not_available")' v-bind:key=hero.name>
          <GridItem :hero=hero></GridItem>
          </b-col>
    </b-row>
    <button v-on:click="fetchData">Fetch Data</button>
</b-container>
</template>

<script>
import GridItem from "./GridItem.vue";

export default {
  data: () => ({
    heroes: []
  }),
  components: {
    GridItem
  },
  created: function() {
    this.fetchData();
  },

  methods: {
    async fetchData() {
      const apiKey = process.env.VUE_APP_PUB;
      const response = await fetch(
        `https://gateway.marvel.com/v1/public/characters?limit=16&apikey=${apiKey}`
      );
      const result = await response.json();
      this.heroes = result.data.results;
    }
  }
};
</script>

<style lang="css">
  #myGrid {
    margin-top: 3%
  }
</style>
