<template>
  <v-container>
    <v-row class="mt-4">
      <v-col cols="12" md="6"  class="d-flex flex-column">
        <h2 class="'font-weight-bold'">Ons bedrijf</h2>

          <v-spacer></v-spacer>

        <v-img src="svg/lucky-wear_big__black.svg" alt="Lucky Wear Logo" class="logo-image__desktop"  v-show="$vuetify.display.mdAndUp"></v-img>
      </v-col>

        <v-col cols="12" md="6">
        <p>
          In 2024 hebben wij, een groep enthousiaste ondernemers, ons bedrijf opgericht met één doel voor ogen: iedereen voorzien van hoogwaardig ondergoed, elke maand weer. Met gemak en comfort als onze kernwaarden, bieden wij onze klanten een abonnementsdienst aan die hen in staat stelt om zonder enige moeite premium ondergoed aan huis te ontvangen.
        </p>

          <v-img src="svg/lucky-wear_big__black.svg" alt="Lucky Wear Logo" class="logo-image__mobile py-5"  v-show="$vuetify.display.mdAndDown"></v-img>

          <p>
            Onze missie is om het leven van onze klanten te vereenvoudigen door hen te voorzien van ondergoed dat niet alleen comfortabel is, maar ook van de hoogste kwaliteit. Elke maand selecteren wij zorgvuldig de beste materialen en ontwerpen, zodat onze klanten altijd verzekerd zijn van een product dat aan hun hoogste verwachtingen voldoet.
          </p>
          <p>
            Dankzij onze innovatieve aanpak en klantgerichte strategie, hebben we al snel een loyale klantenkring opgebouwd die ons waardeert om de consistentie en kwaliteit van onze producten. Wij streven ernaar om met onze service het dagelijkse leven van mensen een stukje aangenamer te maken.
          </p>
      </v-col >
    </v-row>

    <v-row class="mt-4">
      <v-col cols="12" md="6">
        <h2 class="font-weight-bold">Ons verhaal</h2>
        <p>
          Wij zijn een bedrijf dat elke maand hoogwaardig mannenondergoed of vrouwenlingerie opstuurt voor een betaalbare prijs. Ons mannenondergoed bestaat voor 95% uit katoen, wat zorgt voor ultiem comfort en duurzaamheid. Onze abonnementsdienst stelt klanten in staat om zonder enige moeite premium ondergoed aan huis te ontvangen, waardoor hun leven een stukje eenvoudiger en comfortabeler wordt.
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'AboutSection',
};
</script>

<style scoped>
.font-weight-bold {
  font-size: 1.5rem;
}
.logo-image {

}

.logo-image__mobile{
  width: 100%;
  max-width: 450px;
  margin-bottom: 1.5rem;
}

.logo-image__desktop{
  max-width: 450px;
  margin-bottom: 0;
}

p {
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}
</style>
