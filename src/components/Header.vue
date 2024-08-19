<template>
  <v-app-bar color="white" app>
    <v-toolbar-title>
      <a href="/">
        <img src="svg/lucky-wear__black.svg" alt="Lucky Wear Logo" class="logo" style="width: 135px">
      </a>    
    </v-toolbar-title>
    <v-spacer v-show="$vuetify.display.smAndUp"></v-spacer>
    <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
      <v-btn v-show="$vuetify.display.smAndDown" rounded style="margin-right: 4px!important;" class="button-class">Probeer nu!</v-btn>
    </a>
    <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
      <v-btn v-show="$vuetify.display.mdAndUp" rounded style="margin-right: 0!important;" class="button-class">Probeer gratis!</v-btn>
    </a>
    <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
  </v-app-bar>


    <v-navigation-drawer
      v-model="drawer"
      location="right"
      color="#F7F8FA"
      app>
      <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" @click="scrollToSection(item.href)">
          <v-list-item-content @click="handleItemClick(item.href)">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <a href="https://www.instagram.com/luckywear_nl?igsh=bzJkbHFiOGdrM2gz" target="_blank" rel="noopener noreferrer">
            <v-icon color="black">mdi-instagram</v-icon>
          </a>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      drawer: false,
      items: [
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
    toggleDrawer() {
      console.log('toggleDrawer called'); // Debugging line
      this.drawer = !this.drawer;
      console.log('Drawer state:', this.drawer); // Debugging line
    },
    scrollToSection(id) {
      const headerHeight = document.querySelector('.v-app-bar').offsetHeight;
      const section = document.querySelector(id);
      const sectionPosition = section.offsetTop - headerHeight;
      window.scrollTo({
        top: sectionPosition,
        behavior: 'smooth',
      });
    },
    handleItemClick(href) {
      this.scrollToSection(href);
      this.drawer = false;
    },
  },
};
</script>

<style scoped>
.logo {
  max-height: 40px;
}
.v-btn {
  margin-right: 10px;
}
</style>

