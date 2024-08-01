<template>
  <v-app>
    <HeaderComponent></HeaderComponent>

    <v-main>
        <HeroSection class="my-5 pb-5"></HeroSection>
        <VoordelenSection class="my-5 py-5"></VoordelenSection>
        <ProductSection class="my-5 py-5"></ProductSection>
        <AanbiedingenSection  class="my-5 py-5"></AanbiedingenSection>
        <AboutSection class="my-5 py-5"></AboutSection>
      <ContactSection class="my-5 py-5"></ContactSection>
    </v-main>

    <FooterComponent></FooterComponent>
  </v-app>
</template>

<script>
import "/public/styles/style.css";
// Components
import HeaderComponent from "@/components/Header.vue";
import HeroSection from "@/components/Hero.vue";
import VoordelenSection from "@/components/Voordelen.vue";
import ProductSection from "@/components/Products.vue";
import AanbiedingenSection from "@/components/Aanbiedingen.vue";
import AboutSection from "@/components/About.vue";
import ContactSection from "@/components/Contact.vue";
import FooterComponent from "@/components/Footer.vue";

export default {
  name: 'App',
  components: {
    FooterComponent,
    ContactSection,
    AboutSection,
    HeaderComponent,
    HeroSection,
    VoordelenSection,
    ProductSection,
    AanbiedingenSection,

  },

  data: () => ({
    //
  }),
}
</script>
