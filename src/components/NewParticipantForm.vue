<template>
  <form @submit.prevent="add()">
    <div class="form-group">
      <label>Firstname</label>
      <input class="form-control" v-model="firstname" type="text" />
    </div>
    <div class="form-group">
      <label>Lastname</label>
      <input class="form-control" v-model="lastname" type="text" /><br>
    </div>
    <button class="btn btn-primary" @click="onSubmittion">Add new participant</button>
  </form>
</template>

<script>
export default {
  data () {
    return {
      firstname: '',
      lastname: ''
    }
  },
  methods: {
    onSubmittion () {
      this.$emit('submit', { firstname: this.firstname, lastname: this.lastname })
    }
  }
}
</script>

<style scoped>
form {
  width: 300px;
}
</style>
