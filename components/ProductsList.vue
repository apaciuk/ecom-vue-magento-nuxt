<template>
<div class="uk-grid-medium uk-width-1-1 uk-text-center uk-margin-large-top" uk-grid>
     <div v-for="product in products" :key="product.id">
      <Products2 :product="product" />
    </div>
    <div v-if="products.length === 0">
      <p>{{ noProductLabel }}</p>
    </div>
  </div>
</template>

<script>
import { getByTitle } from '@/assets/filters';

export default {
  name: 'productsList',
  data () {
    return {
      id: '',
      noProductLabel: 'No product found',
      productsFiltered: []
    };
  },

  computed: {
    products () {
      if (this.$store.state.userInfo.hasSearched) {
        return this.getProductByTitle();
      } else {
        return this.$store.state.products;
      }
    }
  },

  methods: {
    getProductByTitle () {
      let listOfProducts = this.$store.state.products,
          titleSearched = this.$store.state.userInfo.productTitleSearched;
      
      return this.productsFiltered = getByTitle(listOfProducts, titleSearched);
    }
  }

};
</script>

<style lang="scss" scoped>
  .card {
    margin: 10px;
  }
</style>
