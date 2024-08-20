<template>
  <v-container>
    <v-row class="mt-4">
      <v-col cols="12">
        <v-card class="pa-4 elevation-1">
          <h2 class="headline font-weight-bold" style="font-size: 1.5rem;">Kom in contact</h2>

          <v-card-subtitle>
            Vul het formulier in of kom of mail ons direct en we komen terug op je vraag.
          </v-card-subtitle>
          <v-card-text>
            <v-row class="d-flex justify-center text-center mb-4">
              <v-col cols="12" md="4">
                <v-icon color="blue" size="36">mdi-email</v-icon>
                <p class="font-weight-bold">
                  <a :href="mailtoLink" style="color: black;" class="no-underline">klantenservice@luckywear.nl</a>
                </p>
              </v-col>
              <v-col cols="12" md="4">
                <v-icon color="blue" size="36">mdi-map-marker</v-icon>
                <p class="font-weight-bold">
                  <a :href="locationLink" style="color: black;" class="no-underline">Alkmaar<br>The Netherlands</a>
                </p>
              </v-col>
              <v-col cols="12" md="4">
                <v-icon color="blue" size="36">mdi-instagram</v-icon>
              </v-col>
            </v-row>
            <v-form>
              <v-text-field
                  label="Naam"
                  placeholder="Jouw naam"
                  prepend-inner-icon="mdi-account"
                  outlined
                  dense
              ></v-text-field>
              <v-text-field
                  label="E-mailadres"
                  placeholder="Mail adres"
                  prepend-inner-icon="mdi-email"
                  outlined
                  dense
              ></v-text-field>
              <v-textarea
                  label="Bericht"
                  placeholder="Stel ons je vraag..."
                  outlined
                  dense
              ></v-textarea>
              <v-btn class="button-class mt-3" rounded block>Verstuur bericht</v-btn>
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ContactSection',
  data() {
    return {
      mailtoLink: 'mailto:klantenservice@luckywear.nl',
      locationLink: 'https://www.google.com/maps?q=Alkmaar,The+Netherlands',
    };
  },
};
</script>

<style scoped>
.font-weight-bold {
  font-size: 1.25rem;
}
.button-class {
  background-color: orange;
  color: white;
}

.no-underline {
  color: black;
  text-decoration: none;
}
</style>
