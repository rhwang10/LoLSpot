<template>
  <table class="table">
    <thead>
      <tr>
        <th>Account ID</th>
        <th>Name</th>
        <th>Summoner Level</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>{{accountId}}</td>
        <td>{{name}}</td>
        <td>{{summonerLevel}}</td>
      </tr>
      <!-- <tr v-for="profile in profiles" track-by="id">
        <td>{{profile.name}}</td>
        <td>{{profile.description}}</td>
        <td>{{profile.date}}</td>
        <td><button v-on:click="loadSummoner()">Click to get Summoner</button></td>
      </tr> -->
    </tbody>
  </table>
  <!-- <tbody>
    <div class="columns medium-3" v-for="profile in profiles" track-by="id">
      <div class="card">
        <div class="card-divider">
          {{profile.name}}
        </div>
        <div class="card-section">
          {{profile.description}}
          {{profile.date}}
        </div>
      </div>
    </div>
  </tbody> -->
</template>

<script>
export default {
  data() {
    return {
      profiles: [
        {
          id:'1',
          name: 'Test 1',
          description: 'Test 1 desc',
          date: '1/1/1111'
        },
        {
          id:'2',
          name: 'Test 2',
          description: 'Test 2 desc',
          date: '2/1/1111'
        },
        {
          id:'3',
          name: 'Test 3',
          description: 'Test 3 desc',
          date: '3/1/1111'
        }
      ]
    }
  },
  props: ['accountId', 'name', 'summonerLevel']
}

</script>

<style>
table {
  border-collapse: separate;
  border-spacing: 120px;
}

td {
  padding: 20px 0;
}

</style>
