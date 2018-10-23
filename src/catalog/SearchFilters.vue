<template lang="html">
    <b-form-group label="">
      <b-form-radio-group id="radios1" v-model="selected" :options="options" name="radioOpenions">
      </b-form-radio-group>
  </b-form-group>
</template>

<script>
export default {
  data: () => ({
    selected: "characters",
    options: [
      { text: "Characters", value: "characters" },
      { text: "Comics", value: "comics" },
      { text: "Events", value: "events" },
      { text: "Creators", value: "creators" },
      { text: "Series", value: "series" },
      { text: "Stories", value: "stories" }
    ]
  })
};
</script>

<style lang="css">
</style>
