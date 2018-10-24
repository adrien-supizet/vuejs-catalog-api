<template lang="html">
        <b-card class="card"
                v-if:thumbnail
                v-bind:img-src=thumbail
                img-alt="Img"
                img-top>{{item.name}}
        </b-card>
</template>

<script>
export default {
  data: () => ({}),
  props: {
    item: {
      type: Object,
      default: {}
    }
  },
  computed: {
    thumbail() {
      if (this.item.thumbnail.path.includes("image_not_available")) {
        return false;
      }
      return this.item.thumbnail.path + "." + this.item.thumbnail.extension;
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
