<template>
  <div>
    <b-modal
      id="modal-prevent-closing1"
      hide-footer
      ref="my-modal"
      title="Add Form"
    >
      <form ref="form">
        Name:
        <b-form-input
          title="name"
          id="name-input"
          v-model="userEdit.name"
        ></b-form-input>
        Age:
        <b-form-input
          title="age"
          type="number"
          id="age-input"
          v-model="userEdit.age"
        ></b-form-input>
        Address:
        <b-form-input
          title="address"
          id="address-input"
          v-model="userEdit.address"
        ></b-form-input>
        Phone:
        <b-form-input
          title="phone"
          id="phone-input"
          type="number"
          v-model="userEdit.phone"
        ></b-form-input>
      <b-button class="mt-3" variant="outline-danger" block v-on:click="Add">Add</b-button>
      </form>
    </b-modal>
  </div>
</template>
<script>
export default {
  data () {
    return {
      userEdit: {
        id: this.usersAdd.length,
        name: '',
        age: null,
        address: '',
        phone: ''
      },
      listImg: [
        { name: 'img1', src: '../assets/1.png' },
        { name: 'img2', src: '../assets/2.png' },
        { name: 'img3', src: '../assets/3.png' },
        { name: 'img4', src: '../assets/4.png' },
        { name: 'img5', src: '../assets/5.png' }
      ]
    }
  },
  props: ['usersAdd'],
  created: function () {
  },
  methods: {
    Add () {
      var newCustomer = {
        id: this.userEdit.id + 1,
        name: this.userEdit.name,
        age: this.userEdit.age,
        address: this.userEdit.address,
        phone: this.userEdit.phone
      }
      this.usersAdd.push(newCustomer)
      this.$refs['my-modal'].hide()
    }
  }
}
</script>
