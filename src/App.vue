import { setupMaster } from "cluster"

<template>
  <div id="app">
    <button @click="sumar">Sumas</button>
    <button @click="multiplicar">Multiplicaciones</button>
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
  margin-top: 60px;
  height:1000px;
  width:2000px;
  background-image:url("./assets/mario.jpg");
  //background-position-x: -400px;
  //background-color: black;
}
</style>
