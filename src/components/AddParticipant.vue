<template>
    <div>
      <input v-model="participantName" type="text" placeholder="Nombre del participante">
      <button @click="addParticipant">Agregar</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        participantName: ''
      };
    },
    methods: {
      addParticipant() {
        if (this.participantName.trim() !== '') {
          this.$emit('participant-added', this.participantName.trim());
          this.participantName = '';
        }
      }
    }
  };
  </script>
  