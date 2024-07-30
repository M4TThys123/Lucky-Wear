<template>
  <v-container>
    <v-row class="mt-4">
      <v-col cols="12">
        <h1 class="font-weight-bold">Mannen ondergoed</h1>
        <p class="price">€14,95 p.m.</p>
        <v-rating v-model="rating" readonly color="amber" background-color="amber"></v-rating>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="d-flex justify-center mb-4">
        <v-carousel v-model="selectedImage" show-arrows class="main-image carousel-shadow">
          <v-carousel-item v-for="(image, index) in images" :key="index" :value="index">
            <v-img :src="image.src" :alt="image.alt" class="main-image"></v-img>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
    <v-row>
      <v-col v-for="(image, index) in images" :key="index" cols="6" class="d-flex justify-center mb-2">
        <v-img :src="image.src" :alt="image.alt" class="small-image shadow" @click="selectedImage = index"></v-img>
      </v-col>
    </v-row>
    <v-row class="my-4">
      <v-col cols="12">
        <v-btn class="button-class" rounded>Probeer nu gratis!</v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <p class="mb-5">
          Onze ondergoed is vervaardigd uit een hoogwaardige mix van 95% katoen en 5% spandex, wat zorgt voor een comfortabele en flexibele pasvorm. Het product heeft een solide patroon en is gemaakt van gebreide stof, wat bijdraagt aan de duurzaamheid en ademende eigenschappen. Onder de categorie Boxers & Briefs, is dit ondergoed specifiek ontworpen voor volwassenen en biedt het verschillende functionaliteiten zoals antibacterieel, antistatisch, ademend, duurzaam en snel droog.
        </p>
        <v-expansion-panels class="my-5">
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
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ProductSection',
  data() {
    return {
      selectedImage: 0,
      rating: 5,
      images: [
        { src: 'images/product-front.jpg', alt: "Men's Underwear" },
        { src: 'images/product-packages.png', alt: 'Men\'s Underwear Small' },
      ],
    };
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
</style>
