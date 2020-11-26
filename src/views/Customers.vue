<template>
  <div>
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
          <b-td variant="dark">
            <b-icon icon="person-plus" scale="2" v-b-modal.modal-prevent-closing1 v-on:click="edt(user.id)"></b-icon>
          </b-td>
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
        <Add :usersAdd="users" />
      </b-tbody>
    </b-table-simple>
    </div>
  </div>
</template>
<script>
import Update from '../components/frmCustomerUpdate'
import Add from '../components/frmCustomerAdd'
export default {
  components: {
    Update,
    Add
  },
  data () {
    return {
      list: [
        { id: 1, name: 'Chu Đức Anh', age: 21, address: 'Bắc Giang', phone: '0989405152', img: '../assets/1.png' },
        { id: 2, name: 'Trần Tuấn Anh', age: 21, address: 'Nam Định', phone: '0989450153', img: '../assets/2.png' },
        { id: 3, name: 'Đinh Viết Ninh', age: 21, address: 'Bắc Ninh', phone: '0989450154', img: '../assets/3.png' },
        { id: 4, name: 'Đỗ Xuân Hoàng', age: 21, address: 'Hà Nội', phone: '0989450155', img: '../assets/4.png' }
      ],
      user: {
        id: -1,
        name: 'Chu',
        age: -1,
        address: 'BG',
        phone: '0123',
        img: ''
      },
      usertmp: {
        id: -1,
        name: '',
        age: -1,
        address: '',
        phone: '',
        img: ''
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
