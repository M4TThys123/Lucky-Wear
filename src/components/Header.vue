<template>
  <div class="header-wrapper">
    <v-app-bar color="white" app>
      <!-- Logo -->
      <v-toolbar-title>
        <a href="/">
          <img src="svg/lucky-wear__black.svg" alt="Lucky Wear Logo" class="logo" style="width: 135px">
        </a>
      </v-toolbar-title>

      <!-- Centered Navigation Links (as List Items) -->
      <div class="centered-nav" v-show="$vuetify.display.mdAndUp">
        <v-list dense>
          <v-list-item
              v-for="item in items"
              :key="item.title"
              @click="handleItemClick(item.href)"
          >
            <v-list-item-content>
              <a :href="item.href" class="nav-link">{{ item.title }}</a>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </div>

      <!-- Instagram Icon -->
      <v-btn icon href="https://www.instagram.com/luckywear_nl?igsh=bzJkbHFiOGdrM2gz" target="_blank" rel="noopener noreferrer" v-show="$vuetify.display.mdAndUp">
        <v-icon color="black">mdi-instagram</v-icon>
      </v-btn>

      <!-- Mobile CTA Button -->
      <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
        <v-btn v-show="$vuetify.display.smAndDown" rounded  style="margin-right: 4px!important;" class="button-class">Probeer nu!</v-btn>
      </a>

      <!-- Desktop CTA Button -->
      <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
        <v-btn v-show="$vuetify.display.mdAndUp" rounded style="margin-right: 0!important;" class="button-class">Probeer gratis!</v-btn>
      </a>

      <!-- Mobile Hamburger Icon -->
      <v-app-bar-nav-icon
          @click="toggleDrawer"
          v-show="$vuetify.display.smAndDown"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <!-- Mobile Drawer Navigation -->
    <v-navigation-drawer
        v-model="drawer"
        location="right"
        color="#F7F8FA"
        app
    >
      <v-list dense>
        <v-list-item
            v-for="item in items"
            :key="item.title"
            @click="scrollToSection(item.href)"
        >
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
  </div>
</template>

<script>
import { useDisplay } from 'vuetify';

export default {
  name: "HeaderComponent",
  setup() {
    const { mdAndDown } = useDisplay();
    return {
      isSmallScreen: mdAndDown,
    };
  },
  data() {
    return {
      drawer: false,
      items: [
        { title: "Home", href: "#hero-section", mobileOnly: true },
        { title: "Voordelen", href: "#voordelen-section", mobileOnly: true },
        { title: "Producten", href: "#product-section" },
        { title: "Aanbiedingen", href: "#aanbiedingen-section" },
        { title: "Over", href: "#about-section" },
        { title: "Contact", href: "#contact-section" },
      ],
    };
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },
    scrollToSection(id) {
      const headerHeight = document.querySelector(".v-app-bar").offsetHeight;
      const section = document.querySelector(id);
      const sectionPosition = section.offsetTop - headerHeight;
      window.scrollTo({
        top: sectionPosition,
        behavior: "smooth",
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
/* Center the navigation between logo and Instagram icon */
.centered-nav {
  display: flex;
  justify-content: center;
  flex-grow: 1;
  /*gap: 20px;*/
}

.centered-nav .v-list {
  display: flex;
  /*gap: 20px; !* Spacing between items *!*/
}

.nav-link {
  text-decoration: none;
  color: black;
  font-weight: 500;
}

.nav-link:hover {
  color: orange;
}

/* Styling for the desktop CTA button */
.cta-desktop-button {
  background-color: white !important;
  color: orange !important;
  border: 2px solid orange;
  margin-right: 15px;
}

/* Adjust button for hover state */
.cta-desktop-button:hover {
  background-color: orange !important;
  color: white !important;
}

/* Mobile-specific styles */
@media (max-width: 960px) {
  .v-app-bar-nav-icon {
    display: block;
  }

  .centered-nav, .cta-desktop-button {
    display: none;
  }
}

/* Adjust logo size */
.logo {
  max-height: 40px;
}

/* General toolbar layout */
.v-toolbar__content {
  margin: 0 auto !important;
  max-width: 1400px !important;
}

.header-inner {
  max-width: 1400px;
  margin: 0 auto;
}
</style>