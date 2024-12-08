<template>
    <div>
      <h2>Dino Discovery - Mesozic era</h2>
      <ul class="dino_grid">
        <li v-for="dino in dinos" :key="dino.id">
          <h3>{{ dino.species }}</h3>
          <p>Period: {{ dino.period }}</p>
          <p>Height: {{ dino.height }}</p>
          <p>Type: {{ dino.type }}</p>
          <p>Region: {{ dino.region }}</p>
          <p>Year discovered: {{ dino.year_discovered }}</p>
          <a :href="dino.url" target="_blank">Learn More</a>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['dinos']
  };
  </script>
  
  <style scoped>
  .dino_grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    padding: 20px;
    margin-top: 0;
  }
  h2 {
    padding-left: 20px;
    margin-bottom: 0%;
  }
  ul {
    list-style: none;
    padding: 0;
  }
  li {
    background-color: rgb(244, 199, 165);
    margin: 10px 0;
    border: 1px solid #ddd;
    padding: 10px;
  }
  /* Switch to one column for smaller screen sizes */
  @media (max-width: 700px) {
  .dino_grid {
    grid-template-columns: 1fr; 
  }
}
  </style>

  
  