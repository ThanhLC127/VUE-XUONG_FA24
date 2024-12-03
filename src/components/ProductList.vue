<script setup>
import { ref } from 'vue';
import ProductItem from './ProductItem.vue';

const products = ref([]);
const urlProducts = 'https://673b52a6339a4ce4451bb39e.mockapi.io/product';

function formatPrice(price) {
  return new Intl.NumberFormat('vi-VN').format(price) + ' VND';
}
async function getProducts() {
  products.value = await (await fetch(urlProducts)).json()
}
getProducts();

</script>

<template>
  <div class="container">
    <h1>Danh sách sản phẩm</h1>

    <!-- Hiển thị danh sách -->
    <div class="row">
      <div class="col-3 g-3" v-for="product in products" :key="product.id">
        <ProductItem>
          <template #productName> {{ product.name }} </template>
          <template #productPrice> {{ formatPrice(product.price) }} </template>
        </ProductItem>
      </div>
    </div>

  </div>

</template>
