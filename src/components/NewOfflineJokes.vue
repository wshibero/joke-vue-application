<template>
  <div>
    <p>{{joke}}</p>
    <button @click='getjoke'>new joke</button>
  </div>
</template>

<script>
  export default{
    data(){
      return{
        jokes: ['Why didn\’t the elf pay his rent? He was a little short.',
           'Why shouldn\’t you eat clowns? They taste funny.',
           'When does a dad joke become a dad joke? When it becomes apparent.',
           'A bossy man walked into a bar. Then ordered everyone a round.',
           'I only catch cold on weekdays. Probably because I have a weekend immune system.',
           'Why did the roofer go to the doctor? He had shingles.'],
        joke: ''
      }
    },
    methods:{
      getjoke(){
        this.joke = this.jokes[Math.floor(Math.random() * this.jokes.length)]
      }
    }
  }
</script>
