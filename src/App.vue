<template>
  <v-app>
    <HeaderComponent></HeaderComponent>
    <v-main>
        <HeroSection class="my-5 pb-5"></HeroSection>
        <VoordelenSection class="my-5 py-5"></VoordelenSection>
        <ProductSection class="my-5 py-5"></ProductSection>
    </v-main>
  </v-app>
</template>

<script>
import "/public/styles/style.css";
// Components
import HeaderComponent from "@/components/Header.vue";
import HeroSection from "@/components/Hero.vue";
import VoordelenSection from "@/components/Voordelen.vue";
import ProductSection from "@/components/Products.vue";

export default {
  name: 'App',
  components: {
    HeaderComponent,
    HeroSection,
    VoordelenSection,
    ProductSection,
  },

  data: () => ({
    //
  }),
}
</script>
