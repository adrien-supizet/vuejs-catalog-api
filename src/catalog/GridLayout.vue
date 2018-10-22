<template lang="html">
  <b-container class="bv-example-row">
    <b-row>
        <b-col class sm="4" md="3" v-for='hero in heroes' v-bind:key=hero.name>
          <GridItem :name=hero.name></GridItem>
          </b-col>
    </b-row>
    <button v-on:click="fetchData">Fetch Data</button>
</b-container>
</template>

<script>
import axios from 'axios';
import GridItem from './GridItem.vue';

export default {
  data: () => ({
    heroes: []
  }),
  components: {
    GridItem
  },
  methods: {
    async fetchData() {
      const response = await fetch('https://swapi.co/api/people/');
      const data = await response.json();
      this.heroes = data.results;
      console.log(this.heroes);
    }
  }
};
</script>

<style lang="css">
b-col {
}
</style>
