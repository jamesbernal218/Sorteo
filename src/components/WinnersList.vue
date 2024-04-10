<template>
    <div>
      <h2>Ganadores</h2>
      <ul>
        <li v-for="(winner, index) in winners" :key="index">{{ winner }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['winners']
  };
  </script>
  