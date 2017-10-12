<template>
    <div class="ui container">
      <table class="ui celled table">
        <thead>
          <th>Date</th>
          <th>Event</th>
        </thead>
        <tbody>
          <tr v-for="new$ in news">
            <td>
              <h4 class="ui image header"></h4>
              <div class="content">
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
    
</style>