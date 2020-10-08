import { setupMaster } from "cluster"

<template>
  <div id="app">
    <!-- <button @click="sumar">Sumas</button> -->
    <button class="option" @click="multiplicar">Multiplicaciones</button>
    <Tablas v-if="multiplicaciones" msg="Multiplicaciones"/>
    <Sumas v-if="sumas"></Sumas>
  </div>
</template>

<script>
import Tablas from './components/Tablas.vue'
import Sumas from './components/Sumas.vue'

export default {
  name: 'app',
  components: {
    Tablas,
    Sumas
  },
  data(){
    return{
      sumas: false,
      multiplicaciones: false
    }
  },
  methods: {
    sumar() {
      this.sumas = true
      this.multiplicaciones = false
    },
    multiplicar(){
      this.multiplicaciones = true
      this.sumas = false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  min-height:100vh;
  width:100%;
  /* background-image:url("./assets/mario.jpg");
  background-position-x: -400px; */
  background-color: #333;
}
.option {
    min-width: 150px;
    padding: 8px;
    background-color: white;
    color: black;
    margin-top: 5px;
    border: none;
    border-radius: 3px;
}
.option:hover {
  background-color: #333;
  color: white;
}
body{margin:0;}
</style>
