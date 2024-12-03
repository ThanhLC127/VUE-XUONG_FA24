<script setup>
import { BIconCart, BIconEye } from 'bootstrap-icons-vue';
</script>

<template>
  <div class="card">
    <img class="card-image-top" src="https://placehold.co/150" alt="NoImage" width=100% />
    <div class="card-body">
      <h4 class="card-title">
        <slot name="productName"></slot>
      </h4>
      <p class="card-text">
        <slot name="productPrice"></slot>
      </p>
      <RouterLink to="/product/1" class="btn btn-success">
        <BIconEye />
      </RouterLink>
      <button class="btn btn-warning ml-2">
        <BIconCart />
      </button>
    </div>
  </div>
</template>
