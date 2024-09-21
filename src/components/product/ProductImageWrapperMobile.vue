<template>
  <!-- Carousel image -->
  <v-row>
    <v-col cols="12" class="d-flex justify-center mb-4">
      <v-carousel
          v-model="selectedImage"
          show-arrows-on-hover
          hide-delimiters
          class="main-image carousel-shadow"
          height="300"
      >
        <v-carousel-item
            v-for="(image, index) in currentImages"
            :key="index"
            :value="index"
        >
          <v-img :src="image.src" :alt="image.alt" class="main-image"></v-img>
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </v-row>

  <!-- Thumbnail images -->
  <v-row>
    <v-col
        v-for="(image, index) in currentImages"
        :key="index"
        cols="6"
        class="d-flex justify-center mb-2"
    >
      <v-img
          :src="image.src"
          :alt="image.alt"
          class="small-image shadow"
          @click="$emit('update:selectedImage', index)"
      ></v-img>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "ProductImageWrapperMobile",
  props: {
    currentImages: {
      type: Array,
      required: true,
    },
    selectedImage: {
      type: Number,
      required: true,
      default: 0,
    },
  },
};
</script>

<style scoped>
.main-image {
  width: 100%;
  border-radius: 12px;
}
.small-image {
  width: 100%;
  border-radius: 12px;
  cursor: pointer;
}
.small-image[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
}
.carousel-shadow {
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}
</style>