<template>
  <div class="hello">
    <button class="practice" v-on:click="multiplicar">
      Practicar
    </button>

    <Multiplicaciones v-if="!showMultiplicaciones"></Multiplicaciones>
    <Examen v-if="showMultiplicaciones"></Examen>
  </div>
</template>

<script>
  import Multiplicaciones from "./Multiplicaciones.vue"
  import Examen from "./Examen.vue"
  export default {
  name: 'Tablas',
  components:{
    Multiplicaciones,
    Examen
  },
  props: {
    msg: String
  },
  data() {
    return {
      showMultiplicaciones: false,
    }
  },
  methods: {
    multiplicar() {
      this.showMultiplicaciones = !this.showMultiplicaciones
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
.practice{
  min-width: 150px;
    padding: 8px;
    background-color: white;
    color: black;
    margin: 10px 0px;
    border: none;
    border-radius: 3px;
}
.practice:hover {
  background-color: #333;
  color: white;
}
</style>
