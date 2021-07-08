<template>
  <div id="app">
    <h2 class="title">{{msg}} {{score}}</h2>

    <input type="text" v-model="firstname">
    {{firstname}}
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data: function() {
    return {
      msg: "Prout Prout!",
      firstname: "",
      score: 0
    }
  } 
}
</script>

<style>
  .title {
    color: red;
  }
</style>
