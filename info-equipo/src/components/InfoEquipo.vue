<template>
  <div>
    <p>Nombre del equipo: {{ equipo }}</p>
    <p>Nombre corto: {{ nombreCorto }}</p>
    <p>Fecha de creacion: {{ fecha }}</p>
    <p>Deporte: {{ deporte }}</p>
    <p>Liga: {{ liga }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      equipo: "",
      nombreCorto: "",
      fecha: "",
      deporte: "",
      liga: "",
    };
  },

  props: ["idTeam"],

 
  

  watch: {
    idTeam: {
      handler: function() {
         return axios.get(`https://www.thesportsdb.com/api/v1/json/1/searchteams.php?t=${this.idTeam}`)
         .then((response)=>{
             this.equipo = response.data.teams[0].strTeam;
             this.nombreCorto = response.data.teams[0].strTeamShort
             this.fecha = response.data.teams[0].intFormedYear
             this.deporte = response.data.teams[0].strSport
             this.liga = response.data.teams[0].strLeague
         })         
      },
    },
  },
};
</script>

<style></style>
