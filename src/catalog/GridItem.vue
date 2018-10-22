<template lang="html">
<span>{{name}}</span>
</template>

<script>
export default {
  data: () => ({}),
  props: {
    name: {
      type: String,
      default: 'Unknown'
    }
  }
};
</script>

<style lang="css">
</style>
