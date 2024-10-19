<script setup>
import { inject } from 'vue'
import CartItem from './CartItem.vue'
import { vAutoAnimate } from '@formkit/auto-animate'
const { cart, removeFromCart } = inject('cart')
</script>

<template>
  <div v-auto-animate class="flex flex-col gap-5 flex-1 justify-between">
    <CartItem
      v-for="item in cart"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :image-url="item.imageUrl"
      @on-click-remove="() => removeFromCart(item)"
    />
  </div>
</template>
