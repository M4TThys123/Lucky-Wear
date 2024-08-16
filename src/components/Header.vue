<template>
  <v-app-bar color="white" app>
    <v-toolbar-title>
      <img src="svg/lucky-wear__black.svg" alt="Lucky Wear Logo" class="logo" style="width: 135px">
    </v-toolbar-title>
    <v-spacer v-show="$vuetify.display.smAndUp"></v-spacer>
    <v-btn v-show="$vuetify.display.smAndDown" rounded style="margin-right: 4px!important;" class="button-class">Probeer nu!</v-btn>
    <v-btn v-show="$vuetify.display.mdAndUp" rounded style="margin-right: 0!important;" class="button-class">Probeer gratis!</v-btn>
    <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>

    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
      right
      color="#F7F8FA"
      style="z-index: 1000;">
      <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" :href="item.href">
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-icon>mdi-instagram</v-icon>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-app-bar>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      drawer: false,
      items: [
        { title: 'Producten', href: '#product-section' },
        { title: 'Prijzen', href: '#pricing-section' },
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