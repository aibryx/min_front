<template>
  <div id="app">
    <button class="btn" @click="login">Войти</button>
    <div class="response">Response  {{ response }}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      response: ""
    }
  },
  methods: {
    async login() {
      const url = "https://dev.milkhunters.ru/api/v1/docs/"

      const response = await axios.post(url + "signin", {
        "username": "supertest",
        "password": "qwerty1234@"
      })

      this.response = response.data

      console.log(response.data)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.btn {
  background: teal;
  border: 2px solid teal;
  border-radius: 5px;
  color: white;
  width: 100px;
  height: 30px;
}

.response {
  background: teal;
  border: 2px solid teal;
  border-radius: 5px;
  color: white;
  width: 100px;
  height: 30px;
  padding: 10px;
  display: flex;
  align-items: center;
}
</style>
