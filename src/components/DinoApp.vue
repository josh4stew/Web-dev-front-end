<template>
    <div>
      <DinoList :dinos="dinos" />
    </div>
  </template>
  
  <script>
  import DinoList from './DinoList.vue';
  import axios from 'axios';
  
  export default {
    components: { DinoList },
    data() {
      return {
        dinos: []
      };
    },
    mounted() {
      axios.get('https://storied-mermaid-78500d.netlify.app/api')
        .then(response => {
          this.dinos = response.data;
        })
        .catch(error => {
          console.error('Error fetching data:', error);
        });
    }
  };
  </script>
  