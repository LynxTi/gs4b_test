<template>
  <div>
    ProductPage
    <ProductCard v-if="product" :product="product"/>
  </div>
</template>

<script>

import ProductCard from "@/components/product/ProductCard.vue";

const exampleProduct = {
  images: ['main_photo', 'img_1', 'img_2','img_3','img_4','img_5']
}
export default {
  name: 'ProductPage',
  components: {ProductCard},
  data() {
    return {
      product: null
    }
  },
  mounted() {
    this.product = exampleProduct
  }
}
</script>
