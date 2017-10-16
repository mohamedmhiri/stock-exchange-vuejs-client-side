<template>
    <div style="overflow-x:auto;">
      <h2>Actualities</h2>
      <table>
        <thead>
          <th>Date</th>
          <th>Event</th>
        </thead>
        <tbody>
          <tr v-for="new$ in news">
            <td>
              <h4></h4>
              <div>
              {{new$.date}}
              </div>
            </td>
            <td>
              {{new$.info}}
            </td>
          </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'moom-table',
  data () {
    return {
      news: []
    }
  },
  mounted () {
    axios.get('http://localhost:3000/api/news')
    .then(response => {
      console.log(response)
      this.news = response.data
    })
  }
}
</script>

<style lang="scss">
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  text-align: left;
  padding: 8px;
}

tr:nth-child(even){background-color: #f2f2f2}
</style>