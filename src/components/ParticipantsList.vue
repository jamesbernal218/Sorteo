<template>
    <div>
      <h2>Participantes</h2>
      <ul>
        <li v-for="(participant, index) in participants" :key="index">{{ participant }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['participants']
  };
  </script>
  