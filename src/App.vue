<script setup>
  import {ref} from 'vue';
</script>

<template>
  <h1>The Jokes Application</h1>
  <div id='App'>
    <div>
      <button @click="selectDiv('1')">First View</button>
      <button @click="selectDiv('2')">Second View</button>
      <button @click="selectDiv('3')">Third View</button>
    </div>
    <div v-if="selectedDiv === '1'"><OfflineJokes /></div>
    <div v-if="selectedDiv === '2'"><OfflineJokes /></div>
    <div v-if="selectedDiv === '3'"><OfflineJokes /></div>
  </div>
</template>

<script>
  import OfflineJokes from './components/OfflineJokes.vue';

  export default{
    name: 'App',
    components: {
      OfflineJokes
    },
    data() {
      return {
        selectedDiv: '1',
      };
    },
    methods: {
      selectDiv(divNumber) {
        this.selectedDiv = divNumber;
      },
    },
  }
  
</script>