<template>
  <div class="product-images-block">
    <div class="product-images-block__image-wrap">
      <img class="product-images-block__image" v-if="imgPath" :src="getUrlImage(imgPath)" alt="">
    </div>
    <ImagesCarousel :images="images" @change-image="setImagesPath"/>
  </div>
</template>

<script>
import ImagesCarousel from "@/components/ui/carousel/ImagesCarousel.vue";

export default {
  name: 'ProductImagesBlock',
  components: {ImagesCarousel},
  data() {
    return {
    imgPath: ''
    }
  },
  props: {
    images: {
      type: Array,
      default: []
    }
  },
  mounted() {
    this.imgPath = this.images[0]
  },
  methods: {
    getUrlImage(imgName) {
      return new URL(`/src/assets/images/example/${imgName}.svg`, import.meta.url)
          .href;
    },
    setImagesPath(image) {
      this.imgPath = image
    }
  }
}
</script>
