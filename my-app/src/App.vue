<template>
  <div id="app">
    <h2>My awesome list</h2>
   <List :products="products"></List>
  <Form @add-product="onAddProduct"></Form>
  </div>
</template>

<script>
import uuid from 'uuid/v4';
import Form from './components/Form';
import List from './components/List';

export default {
  name: 'app',
  components: {
    Form,
    List
  },
  data() {
    return {
      products: [{
        id: 0,
        name: 'Coffee'
      }, {
        id: 1,
        name: 'Pizza'
      }],
      newProduct: {
        name: ''
      }
    }
  },
  methods: {
    onAddProduct(product) {
      this.products.push(product);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
