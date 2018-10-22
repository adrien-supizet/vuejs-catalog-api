<template lang="html">
    <header>

      <h1><img src="./logo.png">VueJS catalog for Marvel</h1>

      <h2><img src="./marvel.png"><a href="https://developer.marvel.com/docs" target="blank">Marvel API</a></h2>
  </header>
</template>

<script>
export default {};
</script>

<style scoped lang="css">
header {
  margin-left: 100px 10px 0 10px;
}
h1,
h2 {
  display: inline;
}
h1{
  font-size: 3em;
  width: 50px;
}
h2 {
  float: right;
  clear:left;
  font-size:2em;
  margin-top:5px;
}
a {
  text-decoration: none;
}
img {
  height:50px;
  margin: -5px 10px 0 0;
}
</style>
