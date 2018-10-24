<template lang="html">
  <b-container id="myGrid" class="bv-example-row">
    <b-row>
        <b-col class sm="4" md="3" v-for='hero in heroes' v-if='!hero.thumbnail.path.includes("image_not_available")' v-bind:key=hero.name>
          <GridItem :item=hero></GridItem>
        </b-col>
    </b-row>
</b-container>
</template>

<script>
import GridItem from "./GridItem.vue";

export default {
  props: ["type"],
  data: () => ({
    heroes: [],
    typeOfSearch: ""
  }),
  components: {
    GridItem
  },
  created: function() {
    this.typeOfSearch = this.type;
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const apiKey = process.env.VUE_APP_PUB;
      const response = await fetch(
        `https://gateway.marvel.com/v1/public/${
          this.type
        }?limit=16&apikey=${apiKey}`
      );
      const result = await response.json();
      this.heroes = result.data.results;
    }
  }
};
</script>

<style lang="css">
  #myGrid {
  }
</style>
