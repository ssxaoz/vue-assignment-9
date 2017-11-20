<template>
  <div>
    <div class="form-group">
      <label for="fname">First Name</label>
      <input
        type="text"
        id="fname"
        class="form-control"
        v-model="value.firstName"
      >
      <label for="sname">Last Name</label>
      <input
        type="text"
        id="sname"
        class="form-control"
        v-model="value.lastName"
      >
    </div>
  </div>
</template>
<script>
  export default {
    props: ['value']
  }
</script>
<style scoped>
  .form-group {
    padding: 10px;
    margin: -10px -10px 10px -10px;
    background-color: lightblue;
    border-radius: 5px;
  }
</style>
