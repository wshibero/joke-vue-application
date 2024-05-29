<template>
  <h1>Hello World</h1>
  <div id='App'>
    <OfflineJokes />
  </div>
</template>

<script>
  import OfflineJokes from './components/OfflineJokes.vue';

  export default{
    name: 'App',
    components: {
      OfflineJokes
    }
  }
  
</script>