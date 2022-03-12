<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/fakelogo.png"><br><br><br>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/love.png">
          <p>{{this.$root.$data.cart.length}} items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      cartNum: 0,
    }
  },
  // components: {
  //   ProductList
  // method: {
    // cartItemsNum() {
      // this.cartNum = this.$root.$data.cart.length;
    // }
  // }
}
</script>

<style>

#app {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #cee5f2;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #cee5f2;
}

* {
  box-sizing: border-box;
}

body {
  /* font-family: 'Orbitron' sans-serif !important; */
  margin: 50px 100px;
  background-color:#394053;
  
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  /* margin-bottom: 50px; */
  /* background-color: #394053; */
  /* margin: 50 px; */
}

#menu a {
  color: #cee5f2;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 210px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
  /* background-color:#394053; */
}

#side img {
  width: 60px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 30px;
}

.browse {
  margin-right: 20px;
  /* background-color: #394053; */
}

</style>
