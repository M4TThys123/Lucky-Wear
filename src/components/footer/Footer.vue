<template>

  <div class="footer-wrapper">
    <v-footer class="footer" padless>
      <v-container class="pt-10">
        <v-row class=" footer-inner" justify-md="space-between">
          <v-col cols="12" md="3">
            <figure>
              <v-img
                  src="svg/lucky-wear__yellow.svg"
                  alt="Lucky Wear Logo"
                  class="logo"
              ></v-img>
            </figure>
            <p class="location mt-10">Alkmaar<br>The Netherlands</p>

          </v-col>


          <v-col cols="12" md="3" class="">
            <v-list dense style="background: none !important;" >
              <v-list-item  class="list-item mb-2"
                            min-height="22px"
                            height="auto"
                            v-for="(link, index) in links" :key="index"
                            @click="scrollToSection(link.href)"  >
                <v-list-item-title class="list-item">{{ link.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
            <v-btn class="button-class" rounded>Probeer gratis!</v-btn>
          </v-col>
        </v-row>

        <div class="copyright mt-4 footer-bottom">
          <a href="/" class="text-white">
            © 2024 LUCKY WEAR
          </a>
        </div>
      </v-container>
    </v-footer>


  </div>
</template>

<script>
export default {
  name: 'FooterComponent',
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
      const headerHeight = 64;
      const section = document.querySelector(id);
      const sectionPosition = section.offsetTop - headerHeight;
      window.scrollTo({
        top: sectionPosition,
        behavior: 'smooth',
      });
    },
    handleItemClick(href) {
      this.scrollToSection(href);
      this.drawer = false; // Close the drawer after clicking a link
    },
  },
};
</script>

<style scoped>
.footer-wrapper{
  width: 100%;

}
.footer {
  background-color: var(--footer-color-prm)!important;
  color: white;
  padding: 0 !important;
  font-size: 18px !important;
}
.footer-inner{
  padding: 40px;
  margin: 0!important;
}
.location {
  line-height: 22px;
}

.list-item{
  font-size: 18px!important;
  padding: 0!important;
  margin: 0!important;
  color: var(--color-white)!important;
  font-weight: bold !important;
  height: auto!important;
}


.footer-bottom {
  background-color: var(--footer-color-sec)!important;
  padding: 20px!important;
font-size: 12px!important;
  text-align: center!important;
  font-weight: bold!important;
}



.logo {
  width: 100%;
  min-width: 150px;
  max-width: 300px;
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

/* Medium devices (greater than 960px) */
@media (min-width: 961px) {
  .logo {
    max-width: 300px;
  }
}
</style>