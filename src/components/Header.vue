<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
defineProps({
  totalPrice: Number,
})

const emit = defineEmits(['openDrawer'])
</script>

<template>
  <header class="flex justify-between border-b border-slate-200 px-8 py-8">
    <router-link to="/">
      <div class="flex items-center gap-4">
        <img src="/logo.png" alt="Logo" class="w-10" />
        <div>
          <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
          <p class="text-slate-400">Shop Of The Best Crossovok</p>
        </div>
      </div>
    </router-link>
    <ul class="flex items-center gap-10">
      <li
        @click="() => emit('openDrawer')"
        class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black"
      >
        <img src="/cart.svg" alt="Cart" />
        <b>{{ totalPrice }} rub.</b>
      </li>
      <router-link to="/favorites">
        <li
          class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black"
        >
          <img src="/heart.svg" alt="Zakladki" />
          <span>Zakladki</span>
        </li>
      </router-link>
      <li
        class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black"
      >
        <img src="/profile.svg" alt="Profile" />
        <span>Profile</span>
      </li>
    </ul>
  </header>
</template>
