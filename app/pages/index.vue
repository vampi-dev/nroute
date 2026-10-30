<script setup>
const { data: products, pending, error } = await useFetch('/api/products')
</script>

<template>
  <div>
    <h1>Products</h1>

    <p v-if="pending">Loading...</p>
    <p v-else-if="error">Could not load products.</p>

    <div v-else>
      <div v-for="product in products" :key="product.id">
        <h3>{{ product.name }}</h3>
        <p>Price: Rs. {{ product.price }}</p>
      </div>
    </div>
  </div>
</template>
