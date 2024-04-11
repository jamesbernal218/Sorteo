<template>
  <div>
    <AddParticipant @participant-added="addParticipant" />
    <ParticipantsList :participants="participants" />
    <button @click="drawWinners">Realizar sorteo</button>
    <WinnersList :winners="winners" />
  </div>
  <div class="bg-indigo-500">
  <p class="bg-indigo-500">gg</p>
  </div>
</template>

<script>
import AddParticipant from './components/AddParticipant.vue';
import ParticipantsList from './components/ParticipantsList.vue';
import WinnersList from './components/WinnersList.vue';

export default {
  components: {
    AddParticipant,
    ParticipantsList,
    WinnersList
  },
  data() {
    return {
      participants: [],
      winners: []
    };
  },
  methods: {
    addParticipant(name) {
      this.participants.push(name);
    },
    drawWinners() {
      const numberOfWinners = Math.min(3, this.participants.length);
      const shuffledParticipants = [...this.participants].sort(() => Math.random() - 0.5);
      this.winners = shuffledParticipants.slice(0, numberOfWinners);
    }
  }
};
</script>
