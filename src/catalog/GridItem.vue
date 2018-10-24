<template lang="html">
        <b-card class="card"
                v-if:shouldDisplay
                v-bind:img-src=thumbail
                img-alt="Img"
                img-top>{{title}}
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
    title() {
      if (this.item.name) {
        return this.item.name;
      } else if (this.item.title) {
        return this.item.title;
      } else return this.item.fullName;
    },
    thumbail() {
      return this.item.thumbnail
        ? this.item.thumbnail.path.includes("not_available")
          ? ""
          : this.item.thumbnail.path + "." + this.item.thumbnail.extension
        : "";
    },
    shouldDisplay() {
      return this.item.thumbnail.path.includes("image_not_available")
        ? false
        : true;
    }
  }
};
</script>

<style scoped lang="css">
  .card{
    text-align: center;
    font-size: 2vw;
}
  .square {
    padding-bottom:100%;
    overflow:hidden;
    position:relative;
  }
</style>
