<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="container">
      <div class="Logo">
        <RouterLink to="/"><img class="logo" src="./assets/logo.png" alt=""></RouterLink>
      </div>
      <div class="Name"><h1 id="title">MyShop</h1></div>
      <div class="SearchBar">
        <input type="text" class="searchTerm" placeholder="What are you looking for?">
      <button type="submit" class="searchButton">
        <i class="fa fa-search">🔎</i>
     </button>
      </div>
      <div class="Login"><RouterLink to="/login"><button class="btn">Login</button></RouterLink></div>
  </div>
  </header>
  <RouterView />
</template>

<style scoped>

</style>
