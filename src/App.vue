<template>
  <div id="app">
    <aside v-if="showSidebar">Ma sidebar</aside>
    <p v-else>Ce qui va s'afficher quand ma sidebar ne s'affiche pas</p>

    <h2 class="title">{{msg}} {{score}}</h2>

    <input type="text" v-model="firstname">
    <input type="text" v-model="lastname">
    {{firstname}} {{lastname}}
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
      lastname:"",
      score: 0,
      showSidebar: true
    }
  } 
}
</script>

<style>
  .title {
    color: red;
  }
</style>
