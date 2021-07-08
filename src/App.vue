<template>
  <div id="app">
    <aside v-if="showSidebar">Ma sidebar</aside>
    <p v-else>Ce qui va s'afficher quand ma sidebar ne s'affiche pas</p>

    <input type="checkbox" v-model="isBG">
    <p v-if="isBG">Je suis un BG</p>
    <p v-else>Je suis pas un BG</p>

    <h2 class="title">{{msg}} {{score}}</h2>

    <input type="text" v-model="firstname">
    <input type="text" v-model="lastname">
    {{firstname}} {{lastname}}

    <ul>
      <li :key="aliment.id" v-for="aliment in food">
        {{aliment.title}}
      </li>
    </ul>

    <h3 @click="clickMe">Cliquez-moi!</h3>

    <button @click="incrementScore">Cliqué {{score}} fois</button>


    <div>
      <input type="text" v-model="newTask">
      <button @click="addTask">Ajouter tâche</button>
      <ol>
        <li :key="task.id" v-for="task in tasks">
          {{task.content}}
        </li>
      </ol>
    </div>

    <Barbie world="Plastic" />
    <Barbie world="Zgueg" />

    <Player />
    <Player />
    <Player />
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
import Barbie from './components/Barbie';
import Player from './components/Player';

export default {
  name: 'App',
  components: {
    Barbie,
    Player
  },
  methods: {
    clickMe: function() {
      console.log("J'ai été cliqué!");
    },
    incrementScore: function() {
      this.score++;
    },
    addTask: function() {
      // {id: 1, content: "Ma tâche"}
      let currTask = {
        id: uuidv4(),
        content: this.newTask
      };
      this.tasks.push(currTask);
      console.log(this.tasks);
    }
  },
  data: function() {
    return {
      msg: "Prout Prout!",
      firstname: "",
      lastname:"",
      score: 0,
      showSidebar: true,
      isBG: true,
      food: [
        {id:1, title: "Pizza"},
        {id:2, title: "Jambon"},
        {id:3, title: "Framoge"}
      ], 
      tasks : [
        {id: 1, content: "Ma tâche"},
        {id: 2, content: "Ma pistache"}
      ],
      newTask: ""
    }
  } 
}
</script>

<style>
  .title {
    color: red;
  }
</style>
