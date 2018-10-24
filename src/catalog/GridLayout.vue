<template lang="html">
  <b-container id="myGrid" class="bv-example-row">
    <b-row>
        <b-col class cols="6" sm="4" md="3" v-for='item in items' v-if='!item.thumbnail.path.includes("image_not_available")' v-bind:key=item.name>
          <GridItem :item=item></GridItem>
        </b-col>
    </b-row>
</b-container>
</template>

<script>
//
import GridItem from "./GridItem.vue";

export default {
  props: ["type"],
  data: () => ({
    items: []
  }),
  components: {
    GridItem
  },
  created: function() {
    this.typeOfSearch = this.type;
    this.fetchData();
  },
  beforeUpdate: function() {
    console.log(this.items);
  },
  watch: {
    type() {
      this.fetchData();
    }
  },
  methods: {
    async fetchData() {
      const apiKey = process.env.VUE_APP_PUB;
      const response = await fetch(
        `https://gateway.marvel.com/v1/public/${
          this.type
        }?limit=11&apikey=${apiKey}`
      );
      const result = await response.json();
      this.items = result.data.results;
    }
  }
};
</script>

<style lang="css">
  #myGrid {
  }
</style>
