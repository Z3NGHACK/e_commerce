<template>
    <div class="products">
      <h2>Popular Products</h2>
      <div class="product" v-for="product in popularProducts" :key="product.id">
        <img :src="product.image" :alt="product.name" />
        <h3>{{ product.name }}</h3>
        <p>{{ product.price }} $</p>
        <p>Sold: {{ product.countSold }}</p>
      </div>
    </div>
  </template>
  
  <script>
import {useProductStore} from './views/productStore.js'
  
  export default {
    computed: {
      popularProducts() {
        const store = useProductStore();
        return store.getPopularProducts();
      },
    },
  };
  </script>  
  
  <style>
  .products {
    display: flex;
    flex-wrap: wrap;
  }
  .product {
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
  }
  img {
    max-width: 100px;
  }
  </style>
  