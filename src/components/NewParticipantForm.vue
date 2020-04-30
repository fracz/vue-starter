<template>
  <form @submit.prevent="add()">
    <label>Firstname</label>
    <input v-model="firstname" type="text" />
    <label>Lastname</label>
    <input v-model="lastname" type="text" />
    <button>Add new participant</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newParticipant : {}
      };  
    },
  }
};
</script>