<script setup>
  import {ref} from 'vue'
  import OfflineJokes from './components/OfflineJokes.vue'
  // export default{
  //   name: 'App',
  //   components: {
  //     OfflineJokes
  //   }
  // }
</script>

<template>
  <h1>Jokes Application</h1>
  <!--<OfflineJokes/>-->
  <div id="app">
    <!--<NameChanger />-->
  </div>
  <div id='app'>
    <NewOfflineJokes/>
  </div>
</template>

<script>
// import NameChanger from './components/NameChanger.vue';
import NewOfflineJokes from './components/OfflineJokes.vue';

export default {
  name: 'App',
  components: {
    // NameChanger,
    NewOfflineJokes
  }
};
</script>

<style>
  
</style>