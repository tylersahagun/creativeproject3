<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.gender}}</p>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button v-if="!remove" class="auto" @click="addToCart(product)">Add to Cart</button>
        <button v-else class="auto" @click="removeFromCart(product)">Remove From Cart</button>
      </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
  name: 'ProductList',
  props: {
    products: Array,
    displayType: Array,
    remove: Boolean
  },
  methods: {
    addToCart(product) {
        this.$root.$data.cart.push(product);
    },
    removeFromCart(product) {
        this.$root.$data.cart.splice(this.$root.$data.cart.indexOf(product), 1);
    },
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 40px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 8px;
  margin-top: 35px;
  width: 250px;
}

.product img {
  border: 5px solid #cee5f1;
  height: 230px;
  width: 250px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 10px;
}

.info {
  background: #accbe1;
  color: #394053;
  padding: 15px 30px;
  height: 100px;
  /* margin-left:5px; */
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
  /* margin-left:25px; */
}

button {
  height: 50px;
  background: #accbe1;
  color: #394053;
  border:#cee5f2;
  border-style:outset;
}

.auto {
  margin-left: auto;
}
</style>