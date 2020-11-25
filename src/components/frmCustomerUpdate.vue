<template>
  <div>
    <b-modal
      id="modal-prevent-closing"
    >
    <div class="row-md-1 col col-md-9 container-md">
      <b-img class="d-md-flex" src="../assets/logo.png"></b-img>
    </div>
      <form ref="form">
        Name:
        <b-form-input
          title="name"
          id="name-input"
          :value="user.name"
        >{{user.name}}</b-form-input>
        Age:
        <b-form-input
          title="age"
          type="number"
          id="age-input"
          :value="user.age"
        >{{user.age}}</b-form-input>
        Address:
        <b-form-input
          title="address"
          id="address-input"
          :value="user.address"
        >{{user.address}}</b-form-input>
        Phone:
        <b-form-input
          title="phone"
          id="phone-input"
          type="number"
          :value="user.phone"
        >{{user.phone}}</b-form-input>
      </form>
      <b-button class="mt-3" variant="outline-danger" block v-on:click="Update">Update</b-button>
    </b-modal>
  </div>
</template>
<script>
export default {
  data () {
    return {
      userEdit: {
        id: -1,
        name: '',
        age: -1,
        address: '',
        phone: ''
      }
    }
  },
  props: ['user', 'usersUpdate'],
  created: function () {
  },
  methods: {
    Update () {
      this.usersUpdate = null
    }
  }
}
</script>
