<template>
  <v-container>
    <!-- Title, price and rating -->
    <v-row class="mt-4">
      <v-col cols="12" md="6">
        <h1 class="font-weight-bold">{{ selectedCategory === 'men' ? 'Mannen ondergoed' : 'Vrouwen lingerie set' }}</h1>
        <p class="price">{{ selectedCategory === 'men' ? '€14,95 p.m.' : '€29,95 p.m.' }}</p>
        <v-rating v-model="rating" readonly color="amber" background-color="amber"></v-rating>

      <!-- Image carousel Mobile -->
      <ProductImageWrapperMobile
          v-if="$vuetify.display.smAndDown"
          :current-images="currentImages"
          :selected-image="selectedImage"
      ></ProductImageWrapperMobile>

        <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
          <v-btn class="button-class" rounded>Probeer nu gratis!</v-btn>
        </a>

        <p class="mb-5">
          {{ selectedCategory === 'men' ? menDescription : womenDescription }}
        </p>
        <v-expansion-panels v-model="panels" class="my-5">
          <v-expansion-panel>
            <v-expansion-panel-title>Specificaties</v-expansion-panel-title>
            <v-expansion-panel-text>
              <ul>
                <li><strong>Materiaal:</strong> 95% katoen, 5% spandex.</li>
                <li><strong>Patroon:</strong> Solide.</li>
                <li><strong>Stof:</strong> 95% Gebreide stof.</li>
                <li><strong>Categorie:</strong> Boxers & Briefs Volwassenen.</li>
              </ul>
            </v-expansion-panel-text>
          </v-expansion-panel>
          <v-expansion-panel>
            <v-expansion-panel-title>Functionaliteiten</v-expansion-panel-title>
            <v-expansion-panel-text>
              <ul>
                <li>Antibacterieel</li>
                <li>Antistatisch</li>
                <li>Ademend</li>
                <li>Duurzaam</li>
                <li>Snel droog</li>
              </ul>
            </v-expansion-panel-text>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-col>
      <v-col col="12" md="6"           v-if="$vuetify.display.smAndUp"
    >
        <ProductImageWrapperMobile
          :current-images="currentImages"
          :selected-image="selectedImage"
      ></ProductImageWrapperMobile>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ProductImageWrapperMobile from "@/components/product/ProductImageWrapperMobile.vue";

export default {
  name: "ProductSection",
  components: { ProductImageWrapperMobile },
  data() {
    return {
      selectedCategory: "men",
      selectedImage: 0,
      rating: 5,
      panels: [0, 1], // Open both panels by default
      menImages: [
        { src: "images/product-front.jpg", alt: "Men's Underwear" },
        { src: "images/product-packages.png", alt: "Men's Underwear Small" },
      ],
      womenImages: [
        { src: "images/placeholder.jpg", alt: "Coming Soon", disabled: true },
      ],
      menDescription:
          "Onze ondergoed is vervaardigd uit een hoogwaardige mix van 95% katoen en 5% spandex, wat zorgt voor een comfortabele en flexibele pasvorm. Het product heeft een solide patroon en is gemaakt van gebreide stof, wat bijdraagt aan de duurzaamheid en ademende eigenschappen. Onder de categorie Boxers & Briefs, is dit ondergoed specifiek ontworpen voor volwassenen en biedt het verschillende functionaliteiten zoals antibacterieel, antistatisch, ademend, duurzaam en snel droog.",
      womenDescription:
          "Onze vrouwen ondergoed is vervaardigd uit een hoogwaardige mix van 95% katoen en 5% spandex, wat zorgt voor een comfortabele en flexibele pasvorm. Het product heeft een solide patroon en is gemaakt van gebreide stof, wat bijdraagt aan de duurzaamheid en ademende eigenschappen. Onder de categorie Boxers & Briefs, is dit ondergoed specifiek ontworpen voor volwassenen en biedt het verschillende functionaliteiten zoals antibacterieel, antistatisch, ademend, duurzaam en snel droog.",
    };
  },
  computed: {
    currentImages() {
      return this.selectedCategory === "men" ? this.menImages : this.womenImages;
    },
  },
};
</script>

<style scoped>
.font-weight-bold {
  font-size: 1.5rem;
}
.price {
  font-size: 1.25rem;
  color: gray;
}
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
.button-class {
  background-color: orange;
  color: white;
}
.carousel-shadow {
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}
.v-carousel__content {
  padding-bottom: 0 !important;
}
.v-expansion-panel-content ul {
  padding-left: 1.5rem;
}
.v-expansion-panel-content ul li {
  list-style-type: disc;
}
@media (max-width: 600px) {
  .main-image {
    height: 200px;
  }
}
</style>