<template>
<div>
      <li>{{ product.quote }} </li>
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