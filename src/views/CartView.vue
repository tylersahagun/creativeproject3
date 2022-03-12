<template>
<div>
  <h1>Your Cart </h1>
    <div class="price">
        <!-- <button class="auto" @click="removeFromCart(product)">Remove From Cart</button> -->
        <h2>{{empty()}}</h2>
    </div>
  <ProductList :products="cart" :remove="true"/>
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
    }
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    }
  },
  methods: {
    removeFromCart(product){
      this.$root.$data.cart.splice(product);
    },
    empty() {
        if(this.$root.$data.cart.length == 0){
            return "Your Cart Is Empty";
        }
        return "";
    }
  }
}
</script>