<template>
  <div className="flex justify-between ml-6 mr-6 mt-4" style="padding: 2% 3% 0 3%;">
    <nuxt-link to="/">
      <span class="mt-1 font-semibold text-base leading-tight truncate text-black-700">
        🦖 MinoMart
      </span>
    </nuxt-link>

    <button class="snipcart-checkout flex items-center" style="float: right">
      <Cart/>
      <span class="snipcart-total-price ml-3 font-semibold text-sm text-indigo-500"></span>
    </button>
  </div>
</template>
<script>
import Cart from "./icons/cart.vue"

export default {
  components: {
    Cart
  }
}
</script>

<style>
.emoji {
  font-size: 30px;
}
</style>
