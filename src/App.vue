<script setup>
  import {ref} from 'vue';
</script>

<template>
  <div id='App'>
    <fieldset>
      <div>
        <legend><h1>The Jokes Application</h1></legend>
          <table>
            <tr>
              <td>
                <a class='btnmenu' @click="selectDiv('1')">
                  Computer Stored Jokes
                </a>
              </td>
              <td>
                <a class='btnmenu' @click="selectDiv('2')">
                  User Generated jokes
                </a>
              </td>
              <td>
                <a class='btnmenu' @click="selectDiv('3')">
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
    </fieldset>
  </div>
  <footer>
    &copy 2024. Intellectual property of derrick shibero
  </footer>
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
