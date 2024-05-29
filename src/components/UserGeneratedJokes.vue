<template>
  <h1>User Generated Jokes</h1>
  <div>
    <button @click="div1selected">Display a joke</button>
    <button @click="showDiv(2)">Create New Joke</button>
    <button @click="showDiv(3)">All Jokes</button>

    <div v-if="activeDiv === 2">
      <fieldset>
        <legend>New Joke</legend>
        <input type='text' placeholder='enter a joke' v-model='joke1'/>
        <button @click='submitJoke'>Submit</button>
      </fieldset>
    </div>
    <div v-else-if="activeDiv === 1">
      <p>The joke for now is:
        <br/> {{ijoke}}</p>
    </div>
    <div v-else-if="activeDiv === 3">
      <h2>All Jokes</h2>
      <ul v-if='userjokes.length > 0'>
        <li v-for='userjoke in userjokes'>{{userjoke}}</li>
      </ul>
      <p v-else>There are currently no jokes available</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeDiv: 1,
      joke1: '',
      userjokes: [],
      ijoke: ''
    };
  },
  created(){
    this.displayJoke();
  },
  methods: {
    showDiv(divNumber) {
      this.activeDiv = divNumber;
    },
    submitJoke(){
      if (this.joke1 == ''){
        alert('Please enter a joke')
      }else{
        this.userjokes.push(this.joke1);
        this.joke1 = '';
      }
    },
    displayJoke(){
      if(this.userjokes.length > 0){
        this.ijoke = this.userjokes[Math.floor(Math.random() * this.userjokes.length)]
      }else{
        this.ijoke = 'No jokes yet! Please add some'
      }
    },
    div1selected(){
      this.showDiv(1);
      this.displayJoke();
    }
  },
};
</script>
