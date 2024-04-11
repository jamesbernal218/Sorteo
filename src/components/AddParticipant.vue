<template>
  <div>
    <input v-model="participantName" type="text" placeholder="Nombre del participante" class="border border-gray-300 rounded-lg p-2 mr-2 focus:outline-none focus:border-blue-500">
    <button @click="addParticipant" class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600">Agregar</button>
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
