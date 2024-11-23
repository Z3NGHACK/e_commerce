<template>
    <nav>
      <h2>Categories</h2>
      <ul>
        <li v-for="category in categories" :key="category.id">{{ category.name }}</li>
      </ul>
    </nav>
  </template>
  
  <script>
import {useProductStore} from './views/productStore.js'
  
  export default {
    computed: {
      categories() {
        const store = useProductStore();
        return store.categories;
      },
    },
  };
  </script>
  
  <style>
  nav {
    margin: 20px;
    padding: 10px;
  }
  ul {
    list-style-type: none;
  }
  li {
    cursor: pointer;
  }
  </style>
  