<template>
  <div>
    <div v-if="participantsList!=[]">
      <h1>Participants list</h1>
      <ol>
        <li
          v-for="(participant, index) in participantsList"
          :key="index"
        >{{ participant.firstname}} {{ participant.lastname }}</li>
      </ol>
    </div>

    <h3>New participant</h3>
    <form @submit.prevent="addNewParticipant()">
      <label>Firstname</label>
      <input v-model="firstname" type="text" />
      <label>Lastname</label>
      <input v-model="lastname" type="text" />
      <button>Add new participant</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstname: "",
      lastname: "",
      participantsList: []
    };
  },
  methods: {
    addNewParticipant() {
      console.log({
        firstname: this.firstname,
        lastname: this.lastname
      });

      this.participantsList.push({
        firstname: this.firstname,
        lastname: this.lastname
      });
    }
  }
};
</script>