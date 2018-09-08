<template>
<div>
      <li>{{ product.name }} </li>
</div>
</template>
<script>
  export default {
    name: "ListItem",
    props: {
      product: {
        type: Object
      }
    }
  }
</script>