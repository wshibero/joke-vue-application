<script setup>
  import {ref} from 'vue';
</script>

<template>
  <h1>The Jokes Application</h1>
  <div id='App'>
    <div>
      <table>
        <tr>
          <td>
            <a :class='btnmenu' @click="selectDiv('1')">
              Computer Stored Jokes
            </a>
          </td>
          <td>
            <a :class='btnmenu' @click="selectDiv('2')">
              User Generated jokes
            </a>
          </td>
          <td>
            <a :class='btnmenu' @click="selectDiv('3')">
              From a Joke Api
            </a>
          </td>
        </tr>
      </table>
    </div>
    <div v-if="selectedDiv === '1'">
      <OfflineJokes />
    </div>
    <div v-if="selectedDiv === '2'">
      <UserGeneratedJokes />
    </div>
    <div v-if="selectedDiv === '3'">
      <ApiGeneratedJokes/>
    </div>
  </div>
</template>

<script>
  import OfflineJokes from './components/OfflineJokes.vue';
  import UserGeneratedJokes from './components/UserGeneratedJokes.vue';
  import ApiGeneratedJokes from './components/ApiGeneratedJokes.vue';

  export default{
    name: 'App',
    components: {
      OfflineJokes,
      UserGeneratedJokes,
      ApiGeneratedJokes
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