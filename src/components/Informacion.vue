<template>
  <div class="hello">
    <img v-bind:src=laImagen>
    <h1>{{ elNombre }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Informacion',
  props: {
    elNombre: String,
    laImagen: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1{
  display: inline;
  color: green;
}
h3 {
  margin: 40px 0 0;
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
</style>
