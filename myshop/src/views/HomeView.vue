<template>
    <div class="shop-container">
       <div class="grid">
         <div class="grid-item" v-for="product in products" :key="product.id">
           <img class="img" src="../assets/img_product.png" alt="product.name" />
                <h3 class="product-name">{{ product.name }}</h3>
                <p class="category">{{ product.category }}</p>
                <p class="price">{{ product.price }} €</p>
                <div class="rating">★★★★☆</div>
         </div>
       </div>
    </div>
   </template>
   
   <script>
   import axios from "axios";
   
   export default {
    data() {
       return {
         products: [],
       };
    },
    mounted() {
       this.getProducts();
    },
    methods: {
       async getProducts() {
         try {
           const response = axios.get('http://localhost/api/products')
        .then(response => {
          this.products = response.data['hydra:member'];
          this.products.forEach(product => {
            delete product['@context'];
            delete product['@id'];
            delete product['@type'];
            delete product['hydra:search'];
            delete product['hydra:totalItems'];
          });
        })
        .catch(error => {
          console.error(error);
        });
           console.log(response.data)
           this.products = response.data;
         } catch (error) {
           console.error("Error fetching products: ", error);
         }
       },
    },
   };
   </script>
   
   <style scoped>
   .shop-container {
    padding-top: 5%;
    max-width: 90%;
    margin: 0 auto;
   }
   
   .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(20%, 1fr));
    grid-gap: 20px;
   }
   
   .grid-item {
    border: 1px solid #ccc;
    padding: 20px;
    text-align: center;
   }

   .img {
    width: 70%;
   }
   </style>