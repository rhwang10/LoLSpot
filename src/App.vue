<template>
  <div id="app">
    <input v-model="InputName" placeholder="Enter Summoner Name here">
    <button v-on:click="loadSummoner()">Retrieve Summoner Information</button>
    <profiles v-if="summoner" v-bind="summoner.data"></profiles>
  </div>
</template>

<script>
import Profiles from './components/Profiles'
import apiCall from './components/API.vue'

export default {
  name: 'app',
  data () {
    return {
      InputName: '',
      summoner: null
    }
  },

  components: {
    Profiles
  },

  methods: {
    loadSummoner () {
      if (typeof this.UserInput !== undefined) {
        apiCall.methods.getSummoner(this.InputName, information  => {
          this.summoner = information
          console.log(information)
        })
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
