<template>
  <div>
    <button @click="getUserList">조회</button>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: '',
  components: {},
  data() {
    return {
      userList: []
    }
  },
  setup() {},
  created() {},
  mounted() {
    // this.getUserList()
  },
  unmounted() {},
  methods: {
    async getUserList() {
      this.userList = (await axios.get('http://localhost:3000/users')).data
      // name, email, phone, company, address
      console.log(this.userList)
    }
  }
}
</script>
