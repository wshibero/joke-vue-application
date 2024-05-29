<template>
  <div>
    <h2>Names List</h2>
    <ul>
      <li v-for="(name, index) in names" :key="index">{{ name }}</li>
    </ul>
    <h3>Selected Name: {{ selectedName }}</h3>
    <button @click="changeName">Change Name</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      names: ['Why didn\’t the elf pay his rent? He was a little short.',
       'Why shouldn\’t you eat clowns? They taste funny.',
       'When does a dad joke become a dad joke? When it becomes apparent.',
       'A bossy man walked into a bar. Then ordered everyone a round.',
       'I only catch cold on weekdays. Probably because I have a weekend immune system.',
       'Why did the roofer go to the doctor? He had shingles.'],
      selectedName: ''
    };
  },
  methods: {
    changeName() {
      // Change the selectedName to a random name from the array
      const randomIndex = Math.floor(Math.random() * this.names.length);
      this.selectedName = this.names[randomIndex];
    }
  }
};
</script>

<style scoped>
h2, h3 {
  color: #333;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  padding: 5px 0;
}

button {
  margin-top: 10px;
  padding: 5px 10px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
