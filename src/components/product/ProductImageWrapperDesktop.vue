<template>
  <!--Carousel image-->
  <v-row>
    <v-col cols="12" class="d-flex justify-center mb-4">
      <v-carousel
          v-model="selectedImage"
          show-arrows-on-hover
          hide-delimiters
          class="main-image carousel-shadow"
          height="300"
      >
        <v-carousel-item v-for="(image, index) in currentImages" :key="index" :value="index">
          <v-img :src="image.src" :alt="image.alt" class="main-image"></v-img>
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </v-row>

  <!--Carousel image-->
  <v-row>
    <v-col v-for="(image, index) in currentImages" :key="index" cols="6" class="d-flex justify-center mb-2">
      <v-img :src="image.src" :alt="image.alt" class="small-image shadow" @click="selectedImage = index"></v-img>
    </v-col>
  </v-row></template>

<script>
export default {
  name: "ProductImageWrapperDesktop"
}
</script>

<style scoped>

</style>