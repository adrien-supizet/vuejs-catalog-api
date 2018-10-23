<template lang="html">
  <container class="square">
        <b-card class="card"
                v-if:thumbnail!=""
                v-bind:img-src=thumbail
                img-alt="Img"
                img-top>{{hero.name}}
        </b-card>
      </container>
</template>

<script>
export default {
  data: () => ({}),
  props: {
    hero: {
      type: Object,
      default: {}
    },
    name: {
      type: String,
      default: "Unknown"
    }
  },
  computed: {
    thumbail() {
      if (this.hero.thumbnail.path.includes("image_not_available")) {
        return "";
      }
      return this.hero.thumbnail.path + "." + this.hero.thumbnail.extension;
    }
  }
};
</script>

<style scoped lang="css">
  .card{
    text-align: center;
    font-size: 1vw;
}
  .square {
    padding-bottom:100%;
    overflow:hidden;
    position:relative;
  }
</style>
