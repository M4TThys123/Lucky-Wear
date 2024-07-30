<template>
  <v-app>
    <HeaderComponent></HeaderComponent>
    <v-main>
      <HeroSection></HeroSection>
    </v-main>
  </v-app>
</template>

<script>
import HeaderComponent from "@/components/Header.vue";
import HeroSection from "@/components/Hero.vue";
import "/public/styles/style.css";

export default {
  name: 'App',
  components: {
    HeroSection,
    HeaderComponent,
  },

  data: () => ({
    //
  }),
}
</script>
