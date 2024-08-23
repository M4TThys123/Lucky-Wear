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
                <a :href="mailtoLink" style="color: black;"  target="_blank" class="no-underline">
                  <v-icon color="blue" size="36">mdi-email</v-icon>
                  <p class="font-weight-bold">
                    klantenservice@luckywear.nl
                  </p>
                </a>
              </v-col>
              <v-col cols="12" md="4">
                <a :href="locationLink" target="_blank" style="color: black;" class="no-underline">
                  <v-icon color="blue" size="36">mdi-map-marker</v-icon>
                  <p class="font-weight-bold">
                    Alkmaar<br>The Netherlands
                  </p>
                </a>
              </v-col>
              <v-col cols="12" md="4">
                <a :href="instagramLink"  target="_blank" style="color: black;" class="no-underline">
                  <v-icon color="blue" size="36">mdi-instagram</v-icon>
                </a>
              </v-col>
            </v-row>
            <v-form @submit.prevent="sendEmail">
              <v-text-field
                  v-model="form.name"
                  label="Naam"
                  placeholder="Jouw naam"
                  prepend-inner-icon="mdi-account"
                  outlined
                  dense
              ></v-text-field>
              <v-text-field
                  v-model="form.email"
                  label="E-mailadres"
                  placeholder="Mail adres"
                  prepend-inner-icon="mdi-email"
                  outlined
                  dense
              ></v-text-field>
              <v-textarea
                  v-model="form.message"
                  label="Bericht"
                  placeholder="Stel ons je vraag..."
                  outlined
                  dense
              ></v-textarea>
              <v-btn type="submit" class="button-class mt-3" rounded block>Verstuur bericht</v-btn>
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  name: 'ContactSection',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      mailtoLink: 'mailto:klantenservice@luckywear.nl',
      locationLink: 'https://www.google.com/maps?q=Alkmaar,The+Netherlands',
      instagramLink: 'https://www.instagram.com/luckywear_nl/'
    };
  },
  methods: {
    sendEmail() {
      const serviceID = process.env.VUE_APP_EMAILJS_SERVICE_ID;
      const templateID = process.env.VUE_APP_EMAILJS_TEMPLATE_ID;
      const userID = process.env.VUE_APP_EMAILJS_USER_ID;

      emailjs.send(serviceID, templateID, this.form, userID)
        .then((response) => {
          console.log('SUCCESS!', response.status, response.text);
          alert('Bericht succesvol verzonden!');
        }, (error) => {
          console.log('FAILED...', error);
          alert('Er is een fout opgetreden bij het verzenden van je bericht.');
        });
    }
  }
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
