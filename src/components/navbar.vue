<template>
    <div>
        <b-navbar toggleable="lg" type="dark" variant="info">
            <b-navbar-brand>Vuejs</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
                <template>
                    <div class="h2 mb-0">
                        <b-col md="1">
                            <b-icon v-b-toggle.sidebar-no-header icon="justify" font-scale="1"></b-icon>
                        </b-col>
                    </div>
                </template>
            </b-navbar-nav>
            <b-button-group >
                <b-dropdown variant="info" right text="Khách hàng">
                <b-dropdown-item v-on:click="navigate('listCustomer')">Danh sách khách hàng</b-dropdown-item>
                <b-dropdown-item v-on:click="navigate('addCustomer')">Thêm khách hàng</b-dropdown-item>
                <b-dropdown-divider></b-dropdown-divider>
                </b-dropdown>
                <b-dropdown variant="info" right text="Mua bán">
                <b-dropdown-item v-on:click="navigate('history')">Lịch sử bán hàng</b-dropdown-item>
                <b-dropdown-divider></b-dropdown-divider>
                </b-dropdown>
            </b-button-group>
            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
                <b-nav-form>
                <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
                </b-nav-form>
            </b-navbar-nav>
            </b-collapse>
        </b-navbar>
        <template>
            <b-navbar toggleable type="dark" variant="">
                <b-navbar-brand href="#">{{name}}</b-navbar-brand>
            </b-navbar>
        </template>
    </div>
</template>
<script>
import router from '../router/index'
export default {
  name: 'nav',
  components: {
  },
  methods: {
    navigate (route) {
      if (route === 'listCustomer') {
        router.push({ name: 'Customers' })
      } else if (route === 'addCustomer') {
        route.push({ name: 'Add' })
      } else if (route === 'history') {
        route.push({ name: 'History' })
      }
    }
  },
  props: {
    name: String
  }
}
</script>
