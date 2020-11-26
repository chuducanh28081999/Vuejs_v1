<template>
  <div>
    <div class="row-md-1 col col-md-9  container-md">
      <h3>Vue.js - Display history</h3>
    <b-table-simple striped class="table-primary">
      <b-thead>
        <b-tr>
          <b-td variant="dark">Customer</b-td>
          <b-td variant="dark">Item</b-td>
          <b-td variant="dark">Amount</b-td>
          <b-td variant="dark">Price</b-td>
          <b-td variant="dark">
          </b-td>
        </b-tr>
      </b-thead>
      <b-tbody>
        <b-tr v-for="(i, index) in items" :key="index">
          <b-td>{{i.customer}}</b-td>
          <b-td>{{i.item}}</b-td>
          <b-td>{{i.amount}}</b-td>
          <b-td>{{i.price}}</b-td>
          <b-td>
            <b-icon icon="cart-4" scale="2" v-b-modal.modal-prevent-closing2 v-on:click="getItem(i.id)"></b-icon>
          </b-td>
        </b-tr>
      </b-tbody>
      <Detail :item="itemtmp"/>
    </b-table-simple>
    </div>
  </div>
</template>
<script>
import Detail from '../components/frmHistoryDetail'
export default {
  components: {
    Detail
  },
  data () {
    return {
      list: [
        { id: 1, customer: 'Chu Đức Anh', item: 'Poster', amount: 2, price: 100000, date: '2020-10-28' },
        { id: 2, customer: 'Trần Tuấn Anh', item: 'Pen', amount: 1, price: 10000, date: '2020-11-28' },
        { id: 3, customer: 'Chu Đức Anh', item: 'TeaCup', amount: 1, price: 50000, date: '2020-09-12' },
        { id: 4, customer: 'Trần Tuấn Anh', item: 'Hat', amount: 2, price: 200000, date: '2020-12-25' }
      ],
      item: {
        id: -1,
        customer: '',
        item: '',
        amount: 0,
        price: 0,
        date: ''
      },
      itemtmp: {
        id: -1,
        customer: '',
        item: '',
        amount: 0,
        price: 0,
        date: ''
      },
      items: []
    }
  },
  created: function () {
    this.getList()
  },
  methods: {
    getList () {
      this.items = this.list
    },
    getItem (id) {
      this.items.forEach(i => {
        if (i.id === id) {
          this.itemtmp = i
        }
      })
    }
  }
}
</script>
