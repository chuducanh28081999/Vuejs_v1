<template>
  <div class="home">
    <Navbar />
    <Sidebar />
    <b-img src="../assets/logo.png" />
    <h3>Vuejs</h3>
  </div>
</template>
<script>
import Navbar from '../components/navbar'
import Sidebar from '../components/sidebar'
export default {
  name: 'home',
  components: {
    Navbar,
    Sidebar
  }
}
</script>
