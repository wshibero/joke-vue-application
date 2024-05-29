<template>
  <div>
    <h1>From a Joke Api</h1>
    <p>the Joke is: <br>
      {{ajoke}}
    </p>
    <button @click='fetchData'>New joke</button>
  </div>
</template>

<script>
  export default{
    data(){
      return{
        ajoke: '',
      }
    },
    mounted(){
      this.fetchData();
    },
    methods:{
      async fetchData() {
        try {
          const response = await fetch('https://official-joke-api.appspot.com/jokes/random'); 
          const data = await response.json();
          this.ajoke = data.setup + ' ' + data.punchline;
        } catch (error) {
          alert('Error fetching data:', error);
        }
      },
    }
  }
</script>