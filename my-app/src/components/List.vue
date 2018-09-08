<template>
  <div>
    <ul>
    <ListItem v-for="product in products" :key="product.id" :product="product" ></ListItem>
    </ul>
    <p v-if="!products.length">No products!</p>
  </div>
</template>

<script>
import ListItem from './ListItem';
  export default {
    name: "List",
    components: {
    ListItem
  },
    props: {
      products: {
        type: Array,
      }
    }
  }
</script>