<template>
  <div id="app">
    <HeaderComponent/>
    <SearchFilters id="search" @updateType="onUpdateType"/>
    <GridLayout :type=typeOfSearch />
  </div>
</template>

<script>
import HeaderComponent from "./header/HeaderComponent.vue";
import GridLayout from "./catalog/GridLayout.vue";
import SearchFilters from "./catalog/SearchFilters.vue";

export default {
  name: "app",
  components: {
    HeaderComponent,
    GridLayout,
    SearchFilters
  },
  data: () => ({
    typeOfSearch: "characters"
  }),
  methods: {
    onUpdateType(newType) {
      this.typeOfSearch = newType;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 10px;
}
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#search {
  margin-left: 10%;
}
</style>
