<template>
  <div class="home">
    <b-img src="../assets/logo.png" />
    <h3>Vuejs</h3>
    <h3>{{msg}}</h3>
  </div>
</template>
<script>
export default {
  name: 'home',
  data () {
    return {
      msg: 'Giao diện quản lý khách hàng'
    }
  }
}
</script>
