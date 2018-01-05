<template>
</template>

<script>
import axios from 'axios'
import config from '../../config/config.js'

export default {

  data: function() {
    return {
    }
  },

  methods: {
    getSummoner (summonerName, callback) {
      axios.get(config.naRegionUrl + 'lol/summoner/v3/summoners/by-name/' + summonerName + '?api_key=' + config.apiKey)
      .then(response => {
        callback(response)
      })
      .catch(e => {
        console.log("Error")
      })
    }
  }
}
</script>
