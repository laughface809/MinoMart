<template>
  <div class="flex justify-center m-6">
    <div v-if="this.product !== null">
      <div class="flex flex-col items-center border rounded-lg bg-gray-100">
        <div class="w-full bg-white rounded-lg flex justify-center">
          <img :src="`http://localhost:1337${product.image.url}`" width="375">
        </div>
        <div class="w-full p-5 flex flex-col justify-between">
          <div>
            <h4 class="mt-1 font-semibold text-lg leading-tight truncate text-gray-700">{{product.title}}</h4>
            <div class="mt-1 text-gray-600">{{product.description}}</div>
          </div>

          <button
            class="snipcart-add-item mt-4 bg-white border border-gray-200 d hover:shadow-lg text-gray-700 font-semibold py-2 px-4 rounded shadow"
            :data-item-id="product.id"
            :data-item-price="product.price"
            :data-item-url="`${storeUrl}${this.$route.fullPath}`"
            :data-item-description="product.description"
            :data-item-image="`http://localhost:1337${product.image.url}`"
            :data-item-name="product.title"
            v-bind="customFields">
            Add to cart
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      product: null,
      storeUrl: process.env.storeUrl
    }
  },
  created: async function () {
    const res = await fetch(`http://localhost:1337/products/${this.$route.params.id}`)
    this.product = await res.json()
  }
}
</script>
