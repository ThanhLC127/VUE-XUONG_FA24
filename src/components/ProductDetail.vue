<script setup>
import { ref } from 'vue';

const id = '1';
const urlDetailProduct = 'https://673b52a6339a4ce4451bb39e.mockapi.io/product/' + id;
const product = ref({})
function formatPrice(price) {
  return new Intl.NumberFormat('vi-VN').format(price) + ' VND';
}
async function getProduct() {
  product.value = await (await fetch(urlDetailProduct)).json();
}
getProduct();
</script>

<template>
  <div class="container">
    <h1>{{ product.name }} - {{ product.id }}</h1>
    <p>Quantity: {{ product.quantity }}</p>
    <p>Price: {{ formatPrice(product.price) }}</p>
    <p>{{ product.description }}</p>
  </div>
</template>
