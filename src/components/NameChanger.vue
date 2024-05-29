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
      names: ['Alice', 'Bob', 'Charlie', 'Diana', 'Eve'],
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
