<template>
  <div>
    <Navbar />
    <Sidebar />
    <div class="row-md-1 col col-md-9  container-md">
      <h3>Vue.js - Display a list of customer</h3>
    <b-table-simple striped class="table-primary">
      <b-thead>
        <b-tr>
          <b-td variant="dark">Id</b-td>
          <b-td variant="dark">Name</b-td>
          <b-td variant="dark">Age</b-td>
          <b-td variant="dark">Address</b-td>
          <b-td variant="dark">Phone</b-td>
          <b-td variant="dark"></b-td>
        </b-tr>
      </b-thead>
      <b-tbody>
        <b-tr v-for="(user, index) in users" :key="index">
          <b-td>{{user.id}}</b-td>
          <b-td>{{user.name}}</b-td>
          <b-td>{{user.age}}</b-td>
          <b-td>{{user.address}}</b-td>
          <b-td>{{user.phone}}</b-td>
          <b-td>
            <b-icon icon="person-fill" scale="2" v-b-modal.modal-prevent-closing v-on:click="edt(user.id)"></b-icon>
          </b-td>
        </b-tr>
        <Update :user="usertmp" :usersUpdate="users"/>
      </b-tbody>
    </b-table-simple>
    </div>
  </div>
</template>
<script>
import Update from '../components/frmCustomerUpdate'
import Navbar from '../components/navbar'
import Sidebar from '../components/sidebar'
export default {
  components: {
    Update,
    Navbar,
    Sidebar
  },
  data () {
    return {
      list: [
        { id: 1, name: 'Chu', age: 21, address: 'HaNoi', phone: '0989405152' },
        { id: 2, name: 'Anh', age: 21, address: 'HaNoi', phone: '0989405152' },
        { id: 3, name: 'Duc', age: 21, address: 'HaNoi', phone: '0989405152' }
      ],
      user: {
        id: -1,
        name: 'Chu',
        age: -1,
        address: 'BG',
        phone: '0123'
      },
      usertmp: {
        id: -1,
        name: '',
        age: -1,
        address: '',
        phone: ''
      },
      users: []
    }
  },
  created: function () {
    this.getList()
  },
  methods: {
    getList () {
      this.users = this.list
    },
    edt (id) {
      this.users.forEach(cus => {
        if (cus.id === id) {
          this.usertmp = cus
        }
      })
    },
    del (index) {
      this.users.splice(index, 1)
    }
  }
}
</script>
