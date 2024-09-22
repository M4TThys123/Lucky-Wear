<template>
  <v-container>
    <v-row class="mt-4">
      <v-col cols="12">
        <h2 class="font-weight-bold mb-5">Onze aanbiedingen</h2>
        <p class="subtitle mb-5">
          Profiteer van onze exclusieve abonnementsdiensten voor premium ondergoed en lingerie. Elke maand gemak en topkwaliteit, direct bij je thuis.
        </p>
      </v-col>
    </v-row>
    <div class="elevation-1 rounded-xl">
      <v-row class="offer-row px-5">
        <v-col cols="12" md="4" class="offer-card my-4 pa-0" v-for="offer in offers" :key="offer.title">
          <v-card class="pa-5 elevation-0" rounded="xl">
            <v-card-title class="headline font-weight-bold mb-5 pa-0">{{ offer.title }}</v-card-title>
            <v-card-subtitle class="pa-0">{{ offer.description }}</v-card-subtitle>
            <v-card-text class="pa-0">
              <div class="price large-fon t mt-5">{{ offer.price }}</div>
              <!-- Use outlined property here -->
              <v-btn outlined :class="{'button-class' : offer.bold, 'border-class' : !offer.bold}" class=" mt-3" :href="formLink" target="_blank" rounded>{{ offer.buttonText }}</v-btn>
              <ul class="bullets pl-5 mt-5">
                <li v-for="(benefit, index) in offer.benefits" :key="index" :class="{ 'text-grey': benefit.greyedOut }" class="mt-2">{{ benefit.text }}</li>
              </ul>
            </v-card-text>
            <v-card-actions class="mt-10">
              <!-- Use outlined property here for the second button -->
              <v-btn text outlined color="primary" :href="formLink" target="_blank">{{ offer.callToAction }}</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  name: 'AanbiedingenSection',
  data() {
    return {
      formLink: 'https://eu.jotform.com/form/241725507462355',
      offers: [
        {
          title: 'Vrouwen lingerie set',
          description: 'Comfort en kwaliteit voor de moderne vrouw.',
          price: '€29,95 p.m.',
          buttonText: 'Probeer 30 dagen gratis!',
          benefits: [
            { text: 'Eerste is gratis', greyedOut: false },
            { text: 'u vergoed alleen de verzending van €4,95', greyedOut: true },
            { text: 'Daarna 12 maanden elke maand een onderbroek in de bus voor slechts €29,95', greyedOut: false },
            { text: '2 Weken om uit te testen', greyedOut: false },
            { text: 'Hoogste kwaliteit 95% katoen', greyedOut: false }
          ],
          callToAction: 'Meld je nu aan →',
        },
        {
          title: 'Mannen ondergoed',
          description: 'Ervaar ultieme flexibiliteit met onze maandelijkse opzegoptie.',
          price: '€14,95 p.m.',
          buttonText: 'Probeer 30 dagen gratis!',
          benefits: [
            { text: 'Eerste is gratis', greyedOut: false },
            { text: 'u vergoed alleen de verzending van €4,95', greyedOut: true },
            { text: 'Daarna 12 maanden elke maand een onderbroek in de bus voor slechts €14,95', greyedOut: false },
            { text: '2 Weken om uit te testen', greyedOut: false },
            { text: 'Hoogste kwaliteit 95% katoen', greyedOut: false }
          ],
          callToAction: 'Meld je nu aan →',
          bold: true

        },
        {
          title: 'Maandelijks opzegbaar',
          description: 'Ervaar ultieme flexibiliteit met onze maandelijkse opzegoptie.',
          price: 'Variable prijs',
          buttonText: 'Probeer 30 dagen gratis!',
          benefits: [
            { text: 'Eerste is gratis', greyedOut: false },
            { text: 'u vergoed alleen de verzending van €4,95', greyedOut: true },
            { text: 'Daarna 12 maanden elke maand een onderbroek in de bus voor slechts €14,95', greyedOut: false },
            { text: '2 Weken om uit te testen', greyedOut: false },
            { text: 'Hoogste kwaliteit 95% katoen', greyedOut: false }
          ],
          callToAction: 'Meld je nu aan →'
        }
      ]
    };
  },
  mounted() {
    console.log(this.offers[1].bold);
  }
};
</script>

<style scoped>
.font-weight-bold {
  font-size: 1.5rem;
}
.price {
  font-size: 2rem;
  color: black;
}
.bullets{
  font-size: 18px;
  font-weight: bold;

}
.button-class {
  background-color: orange;
  color: white;
}

.border-class{
  background: none;
  color: var(--color-orange);
  border: 2px solid var(--color-orange);
}
.text-grey {
  color: grey;
}
.offer-card {
  margin-bottom: 1.5rem;
}
h2 {
  text-align: center;
}
.subtitle{
  text-align: center;
  max-width: 944px;
  margin: 0 auto;
  font-size: 18px;
}


.offer-card {
  border-left: 1px solid #ddd;
}

.offer-card:first-child {
  border-left: none;
}

/* On mobile (breakpoint at 600px), we change the border behavior */
@media (max-width: 600px) {
  .offer-card {
    border-left: none;
    border-top: 1px solid #ddd;
  }

  .offer-card:first-child {
    border-top: none;
  }
}
</style>
