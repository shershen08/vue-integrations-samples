<div v-for="i in items">
    <h2>{{i.first_name}} {{i.last_name}}</h2>
    <img :src="i.avatar"/>
</div>

<script>
const axios = require('axios')
export default {
  data () {
      return {
          items: []
      }
  },
  async beforeMount() {
    this.$data.items = await axios.get('https://reqres.in/api/users')
  }
}
</script>