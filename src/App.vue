<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <h2>Komponenten Test</h2>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <v-row align="center">
          <v-col cols="12" sm="6">
            <h2>Tree</h2>
            <v-treeview :items="files" />

            <h2>Select</h2>
            <v-select :items="todos" />
            
            <h2>Slider</h2>
            <v-slider min="0" max="100" v-model="sliderValue" />
            <p> Du hast {{sliderValue}} ausgewählt </p>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import files from './files.json'
import todos from './todos.json'

export default {
  name: 'App',
  data: () => ({
    files,
    todos,
    sliderValue: 25
  }),
  created () {
  },
  methods: {
  }
};
</script>
