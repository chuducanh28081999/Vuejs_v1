<template>
  <div>
    <b-modal
      id="modal-prevent-closing2"
      hide-footer
      ref="my-modal"
      title="Detail cart"
    >
      <form ref="form">
        Customer:
        <b-form-input
          title="custommer"
          id="name-input"
          readonly
          :value="item.customer"
        ></b-form-input>
        Item:
        <b-form-input
          title="item"
          id="item-input"
          readonly
          v-model="item.item"
        ></b-form-input>
        Amount:
        <b-form-input
          title="amount"
          id="amount-input"
          type="number"
          readonly
          v-model="item.amount"
        ></b-form-input>
        Price:
        <b-form-input
          title="price"
          id="price-input"
          type="number"
          readonly
          v-model="item.price"
        ></b-form-input>
        Date:
        <b-form-input
          title="date"
          id="phone-input"
          readonly
          v-model="item.date"
        ></b-form-input>
        <h2>Total: {{total}}</h2>
      <b-button class="mt-3" variant="outline-danger" block v-on:click="close">Close</b-button>
      </form>
    </b-modal>
  </div>
</template>
<script>
export default {
  data () {
    return {
    }
  },
  props: ['item'],
  created: function () {
  },
  computed: {
    total: function () {
      return this.item.price * this.item.amount
    }
  },
  methods: {
    close () {
      this.$refs['my-modal'].hide()
    }
  }
}
</script>
