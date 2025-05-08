<template>
  <div id="app">
    <h1>Vue 3 + FastAPI</h1>
    <button @click="fetchMessage">Fetch Message</button>
    <p>{{ message }}</p>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const message = ref('');

    const fetchMessage = async () => {
      const response = await fetch('http://localhost:8000/api/message');
      const data = await response.json();
      message.value = data.message;
    };

    return { message, fetchMessage };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>