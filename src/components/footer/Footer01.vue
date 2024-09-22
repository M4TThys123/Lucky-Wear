<template>
  <v-footer color="black" padless>
    <v-container>
      <v-row>
        <v-col cols="12" class="text-center">
          <v-img src="images/lucky-wear-logo.png" alt="Lucky Wear Logo" class="logo-image mb-4"></v-img>
          <p class="text-orange">Alkmaar<br>The Netherlands</p>
          <v-list dense style="background: none !important;">
            <v-list-item v-for="(link, index) in links" :key="index" @click="scrollToSection(link.href)">
              <v-list-item-content>
                <v-list-item-title class="text-white">{{ link.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
          <v-btn class="button-class" rounded>Probeer nu gratis!</v-btn>
          <div class="copyright mt-4">
            © 2024 LUCKY WEAR
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  name: 'Footer01Component',
  data() {
    return {
      links: [
        { title: 'Home', href: '#hero-section' },
        { title: 'Voordelen', href: '#voordelen-section' },
        { title: 'Producten', href: '#product-section' },
        { title: 'Aanbiedingen', href: '#aanbiedingen-section' },
        { title: 'Over', href: '#about-section' },
        { title: 'Contact', href: '#contact-section' },
      ],
    };
  },
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
};
</script>

<style scoped>
.logo-image {
  width: 150px;
}
.text-orange {
  color: orange;
}
.text-white {
  color: white;
}
.button-class {
  background-color: orange;
  color: white;
  margin-top: 1rem;
}
.copyright {
  color: white;
  font-size: 0.875rem;
  margin-top: 1.5rem;
}
</style>