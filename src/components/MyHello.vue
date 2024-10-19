<script setup>
defineProps({
  title: String,
  price: Number,
  isAdded: Boolean,
})
</script>

<template>
  <div class="product">
    <h2>Tovar {{ title }}</h2>
    <h3>Price {{ price }}</h3>
    <h3>Added {{ isAdded }}</h3>
    <slot></slot>
  </div>
</template>

<style scoped>
.product {
  border: 1px solid black;
  padding: 10px;
  margin-bottom: 10px;
}
</style>
