<template>
  <div id="app">
    <h2>My awesome list</h2>

   <List :products="sharedState.products"></List>
  <Form @add-product="onAddProduct"></Form>
  </div>
</template>

<script>
import uuid from 'uuid/v4';
import Form from './components/Form';
import List from './components/List';
import axios from 'axios';
import store from './store';

export default {
  name: 'app',
  components: {
    Form,
    List
  },
  created() {
    store.fetchProducts();
  },
  data() {
    return {
      sharedState: store.state
    }
  },
  methods: {
   onAddProduct(product) {
      store.addProduct(product);
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
