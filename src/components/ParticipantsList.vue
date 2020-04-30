<template>
  <ol>
    <li
      v-for="(participant, index) in list"
      :key="index"
    >{{ participant.firstname}} {{ participant.lastname }} <button @click="onRemove(index)" class="btn btn-danger">remove</button></li>
  </ol>
</template>

<script>
export default {
  props: ['list'],
  methods: {
    onRemove (index) {
      this.$emit('remove', index)
    }
  }
}
</script>

<style scoped>

</style>
