<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <h2>Todo App</h2>
    </v-app-bar>

    <v-main>
      <p>
        {{todos}}
      </p>
      <p>
        {{users}}
      </p>
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios'

let apiUrl = 'http://localhost:8888'

export default {
  name: 'App',
  data: () => ({
    users: [],
    todos: []
  }),
  created () {
    this.getUsers()
    this.getTodos()
  },
  methods: {
    async getUsers () {
      try {
        const users = await axios.get(`${apiUrl}/users`)
        this.users = users.data
      } catch (e) {
        console.log(e)
      }
    },
    async getTodos () {
      try {
        const todos = await axios.get(`${apiUrl}/todos`)
        this.todos = todos.data
      } catch (e) {
        console.log(e)
      }
    }
  }
};
</script>
