<template>
  <div>
    <button @click="getUserList">조회</button>
    <button @click="doDelete">삭제</button>
    <simple-grid
      :headers="headers"
      :items="userList"
      selectType="radio"
      checkedKey="id"
      @change-item="doChange"
    />
  </div>
</template>
<script>
import axios from 'axios'
import SimpleGrid from '@/components/SimpleGrid.vue'
export default {
  name: '',
  components: { 'simple-grid': SimpleGrid },
  data() {
    return {
      headers: [
        { title: 'Name', key: 'name' },
        { title: 'Email', key: 'email' },
        { title: 'Phone', key: 'phone' },
        { title: 'Company', key: 'company' },
        // { title: 'Gender', key: 'gender' },
        { title: 'Address', key: 'address' }
      ],
      userList: [],
      chekcedItem: '',
      chekcedItems: []
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
    },
    doChange(data) {
      this.chekcedItem = data
      console.log(data)
    },
    doDelete() {
      // this.chekcedItem
    }
  }
}
</script>
<style scoped>
table {
  width: 100%;
}

table,
th,
td {
  border-collapse: collapse;
}

th,
td {
  border: 1px solid #222;
  padding: 10px;
}
</style>
