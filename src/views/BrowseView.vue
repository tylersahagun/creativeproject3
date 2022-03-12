<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Women')" href="#" class="pure-menu-link">Women</a></li>
      <li class="pure-menu-item"><a @click="select('Men')" href="#" class="pure-menu-link">Men</a></li>
      <!-- <li class="pure-menu-item"><a @click="displayType('')" href="#" class="pure-menu-link">Athletic</a></li> -->
      <!-- <li class="pure-menu-item"><a @click="select('Brazil')" href="#" class="pure-menu-link">Brazil</a></li> -->
    </ul>
  </div>
  <ProductList :products="products" />
  <!-- <ProductList :displayType="displayType" /> -->
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'BrowseView',
  components: {
    ProductList
  },
  data() {
    return {
      gender: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.gender === this.gender);
    },
    // displayType() {
    //   return this.$root.$data.displayType.filter(product =>product.type === 'sport');
    // },
  },
  methods: {
    select(gender) {
        this.gender = gender
    },
    // output(type) {
        // this.type = type;
    // },
  }
}
</script>

<style>

a.pure-menu-link:hover{
    background-color: #4e5668 !important;
}

a.pure-menu-link:active{
    background-color: #4e5668 !important;
}

.pure-menu-link{
    color: #cee5f2 !important;
}

</style>