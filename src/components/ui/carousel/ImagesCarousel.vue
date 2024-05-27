<template>
  <div class="carousel" >
    <div class="carousel__wrapper">
      <div v-for="image in images" class="carousel__img-container" @click="$emit('change-image',image)">
        <img class="carousel__img" :src="getUrlImage(image)" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImagesCarousel',
  props: {
    images: {
      type: Array,
      default: []
    }
  },
  methods: {
    getUrlImage(imgName) {
      return new URL(`/src/assets/images/example/${imgName}.svg`, import.meta.url)
          .href;
    },
    changeImage() {

    }
  }
}
</script>
