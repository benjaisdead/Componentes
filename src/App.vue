<template>
  <div id="app">
    <div v-for="dato in arregloDatos">
      <Informacion v-bind:elNombre="dato.nombre" v-bind:laImagen="dato.imagen" />
    </div>
  </div>
</template>

<script>
import Informacion from './components/Informacion.vue'

export default {
  name: 'App',
  components: {
    Informacion
  },
  data(){
    return{
      arregloDatos:[]
    }
  },
  created(){//método que se invoca cuando se crea la instancia de vue
  fetch('https://rickandmortyapi.com/api/character')
  .then(response => response.json())
  .then(json =>{
    console.log(json);
    console.log(json.results);
    for(let dato of json.results){
      console.log(dato.name);
      console.log(dato.image);
      this.arregloDatos.push({"nombre": dato.name, "imagen": dato.image});
    }
  })
}

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-image: url("./assets/fondo.png");
}
</style>
