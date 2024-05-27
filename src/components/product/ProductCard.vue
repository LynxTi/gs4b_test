<template>
  <div>
    <ProductImagesBlock :images="product.images"/>
  </div>
</template>

<script>
import ProductImagesBlock from "@/components/product/ProductImagesBlock.vue";

export default {
  name: "ProductCard",
  components: {ProductImagesBlock},
  props: {
    product: {
      type: Object,
      required: true
    }
  }
}
</script>
