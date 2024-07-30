<template>
  <v-container class="mt-5">
    <v-row>
      <v-col cols="12">
        <h1 class="display-2 font-weight-bold" style="lineHeight: 1.25">De ultieme ondergoedervaring!</h1>
        <p>
          Bij ons ontvang je elke maand ondergoed en lingerie van topkwaliteit direct bij je thuis.
          Ontdek ongeëvenaard comfort en stijlvolle designs zonder enige moeite. Probeer je eerste setje
          helemaal gratis en ervaar zelf het verschil!
        </p>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="d-flex">
        <v-btn class="button-class" rounded>Probeer gratis!</v-btn>
        <v-btn variant="text">
          <span>Contact</span>
          <v-icon>mdi-arrow-right</v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="d-flex">
        <v-img src="svg/paypal.svg" class="payment-icon" alt="betalings afbeelding: paypal"></v-img>
        <v-img src="svg/visa.svg" class="payment-icon" alt="betalings afbeelding: visa"></v-img>
        <v-img src="svg/credit-card.svg" class="payment-icon" alt="betalings afbeelding: credit-card"></v-img>
        <v-img src="svg/ideal.svg" class="payment-icon" alt="betalings afbeelding: ideal"></v-img>
      </v-col>
    </v-row>
    <v-row style="position: relative">
      <v-col cols="12">
        <v-img src="images/product-package.png" alt="Lucky Wear Package" style="border-radius: 24px" />
      </v-col>
      <div class="image-overlay">
        <div>
          <v-chip prepend-icon="mdi-checkbox-marked-circle"
                  closable
                  variant="elevated">Probeer gratis!
          </v-chip>
        </div>
        <div>
          <v-chip prepend-icon="mdi-alert-circle"
                  closable
                  variant="elevated">Elke maand op de mat!
          </v-chip>
        </div>
      </div>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HeroSection',
};
</script>

<style scoped>
.display-2 {
  font-size: 2rem;
  margin-bottom: 1rem;
}


.payment-icon{
  height: 46.67px;
  max-width: 60px;
  margin-right: 20px;
}
.image-overlay{
  position: absolute;
  width: 100%;
  height: 100%;

  padding: 1.5em;
  gap: 1em;

  display: flex;
  flex-direction: column;
  align-items: flex-end;
  justify-content: flex-end;
}
</style>
