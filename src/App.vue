<script setup>
  import {ref} from 'vue';
</script>

<template>
  <h1>The Jokes Application</h1>
  <div id='App'>
    <div>
      <button @click="selectDiv('1')">Computer Stored Jokes</button>
      <button @click="selectDiv('2')">User Generated jokes</button>
      <button @click="selectDiv('3')">Third View</button>
    </div>
    <div v-if="selectedDiv === '1'">
      <OfflineJokes />
    </div>
    <div v-if="selectedDiv === '2'">
      <UserGeneratedJokes />
    </div>
    <div v-if="selectedDiv === '3'"><OfflineJokes /></div>
  </div>
</template>

<script>
  import OfflineJokes from './components/OfflineJokes.vue';
  import UserGeneratedJokes from './components/UserGeneratedJokes.vue';

  export default{
    name: 'App',
    components: {
      OfflineJokes,
      UserGeneratedJokes
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