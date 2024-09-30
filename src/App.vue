<template>
  <v-app>
      <HeaderComponent></HeaderComponent>

    <v-main>
      <section id="hero-section" class="container">
        <HeroSection class="my-5 pb-5"></HeroSection>
      </section>
      <section id="voordelen-section" class="container">
        <VoordelenSection class="my-5 py-5"></VoordelenSection>
      </section>
     <section id="product-section" class="container">
       <ProductSection class="my-5 py-5"></ProductSection>
     </section>
      <section id="aanbiedingen-section" class="container">
        <AanbiedingenSection class="my-5 py-5"></AanbiedingenSection>
      </section>
      <section id="about-section" class="container">
        <AboutSection class="my-5 py-5"></AboutSection>
      </section>
      <section id="contact-section" class="container">
        <ContactSection class="my-5 py-5"></ContactSection>
      </section>
    </v-main>


    <FooterComponent></FooterComponent>
  </v-app>
</template>

<script>
import "/public/styles/style.css";
// Partials
import HeaderComponent from "@/components/Header.vue";
import FooterComponent from "@/components/footer/Footer.vue";

// Content
import HeroSection from "@/components/Hero.vue";

import VoordelenSection from "@/components/Voordelen.vue";

import ProductSection from "@/components/product/Products.vue";
import AanbiedingenSection from "@/components/Aanbiedingen.vue";
import AboutSection from "@/components/About.vue";
import ContactSection from "@/components/Contact.vue";


export default {
  name: 'App',
  components: {
    // Partials
    HeaderComponent,
    FooterComponent,

    // Content
    HeroSection,

    VoordelenSection,

    ProductSection,
    AanbiedingenSection,
    AboutSection,
    ContactSection,
  },

  data: () => ({
    //
  }),
  methods: {
    scrollToSection(id) {
      const headerHeight = document.querySelector('.v-app-bar').offsetHeight;
      const section = document.querySelector(id);
      const sectionPosition = section.offsetTop - headerHeight;
      window.scrollTo({
        top: sectionPosition,
        behavior: 'smooth',
      });
    },
  },
}
</script>
