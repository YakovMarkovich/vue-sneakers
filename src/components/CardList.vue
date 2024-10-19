<script setup>
import { defineEmits } from 'vue'
import Card from './Card.vue'
import { vAutoAnimate } from '@formkit/auto-animate'

defineProps({
  items: Array,
  isFavorites: Boolean,
})

const emit = defineEmits(['addToFavorite, addToCart '])
</script>

<template>
  <div class="grid grid-cols-4 gap-5" v-auto-animate>
    <Card
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :image-url="item.imageUrl"
      :price="item.price"
      :onClickFavorite="isFavorites ? null : () => emit('addToFavorite', item)"
      :onClickAdd="isFavorites ? null : () => emit('addToCart', item)"
      :is-favorite="item.isFavorite"
      :isAdded="item.isAdded"
    />
  </div>
</template>
