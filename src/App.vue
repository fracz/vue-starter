<template>
  <div>
    <div v-if="participantsList.length !== 0">
      <h1>Participants list</h1>
      <participants-list :list="participantsList" @remove="removeParticipant" />
    </div>
    <h3>New participant</h3>
    <new-participant-form @submit="addNewParticipant" />
  </div>
</template>

<script>
import NewParticipantForm from '@/components/NewParticipantForm.vue'
import ParticipantsList from '@/components/ParticipantsList.vue'

export default {
  data () {
    return {
      participantsList: []
    }
  },
  components: {
    NewParticipantForm,
    ParticipantsList
  },
  methods: {
    addNewParticipant (newParticipant) {
      this.participantsList.push(newParticipant)
    },
    removeParticipant (index) {
      this.participantsList.splice(index, 1)
    }
  }
}
</script>
