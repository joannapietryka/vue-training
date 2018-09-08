<template>
<form @submit.prevent="onSubmit()">
<!--3- 1. name attribute is now required as well as v-validate with its own DSL values -->
<input
  name="product"
  v-model="newProduct.quote"
  v-validate="'required|min:3'"
>
<button>Add</button>
<!--3- 2. errors are added by default when validation is initialized and have some useful methods -->
<div v-show="errors.has('product')">
 {{ errors.first('product') + " hehe" }}
</div>
</form>
</template>

<script>
  import uuid from 'uuid/v4';

  export default {
    name: "Form",

     data() {
      return {
        newProduct: {
          quote: ''
        }
      }
    },
    methods: {
      onSubmit() {
        this.$validator.validateAll().then(result => {
          if (!result) {
            return;
          }

          this.$emit('add-product', {
            id: uuid(),
            ...this.newProduct
          });
          this.newProduct.quote = '';
          this.$validator.reset();
        });
      }
    }
  }
</script>