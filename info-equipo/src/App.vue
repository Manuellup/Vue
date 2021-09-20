<template>
  <div id="app">
    <p>Ingresa id a buscar</p>
    <input type="text" v-model="id" />
    <InfoEquipo :idTeam="id" />
  </div>
</template>

<script>
import InfoEquipo from "./components/InfoEquipo.vue";


export default {
  data() {
    return {
      id: ''
    };
  },


  components: {
    InfoEquipo,
    
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
