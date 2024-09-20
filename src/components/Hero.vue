<template>
  <v-container   >
    <v-row class="mt-md-8 mt-md-10">
      <v-col cols="12" md="6" align-self="center">
        <h1 class="title font-weight-bold">De ultieme ondergoedervaring!</h1>
        <p class="description mb-5">
          Bij ons ontvang je elke maand ondergoed en lingerie van topkwaliteit direct bij je thuis.
          Ontdek ongeëvenaard comfort en stijlvolle designs zonder enige moeite. Probeer je eerste setje
          helemaal gratis en ervaar zelf het verschil!
        </p>
        <v-row class="mt-md-5">
          <v-col cols="12"  class="d-flex">
            <a href="https://eu.jotform.com/form/241725507462355" target="_blank" rel="noopener noreferrer">
              <v-btn class="button-class" rounded>Probeer gratis!</v-btn>
            </a>
            <v-btn variant="text" @click="$root.scrollToSection('#contact-section')" class="contact-btn">
              <span>Contact</span>
              <v-icon>mdi-arrow-right</v-icon>
            </v-btn>
          </v-col>
        </v-row>
        <v-row class="mt-md-10">
          <v-col cols="12" class="d-flex">
            <v-img src="svg/paypal.svg" class="payment-icon" alt="betalings afbeelding: paypal"></v-img>
            <v-img src="svg/visa.svg" class="payment-icon" alt="betalings afbeelding: visa"></v-img>
            <v-img src="svg/credit-card.svg" class="payment-icon" alt="betalings afbeelding: credit-card"></v-img>
            <v-img src="svg/ideal.svg" class="payment-icon" alt="betalings afbeelding: ideal"></v-img>
          </v-col>
        </v-row>
      </v-col>

      <v-col cols="12" md="6" style="position: relative">
        <v-img src="images/product-package_square.png"
               alt="Lucky Wear Package"
               style="border-radius: 24px"
               placeholder
        />

        <div class="image-overlay">
          <div>
            <v-chip class="custom-chip-green" prepend-icon="mdi-checkbox-marked-circle"
                    closable
                    variant="elevated">Probeer gratis!
            </v-chip>
          </div>
          <div>
            <v-chip class="custom-chip-orange" prepend-icon="mdi-alert-circle"
                    closable
                    variant="elevated">Elke maand op de mat!
            </v-chip>
          </div>
        </div>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HeroSection',
};
</script>

<style scoped>
.title {
  font-size: 2rem;
  margin-bottom: 1rem;
  line-height: 1.25em;
}

.description{
  font-size: 18px;
}

.contact-btn{
  font-size: 16px;
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

  /*aspect-ratio: 1 / 1; object-fit: cover;*/
}



</style>



<style scoped>


.desktop-image {
  max-width: 100%;
  border-radius: 24px;
}

.image-overlay {
  position: absolute;
  bottom: 0;
  right: 0;
  padding: 1.5em;
  gap: 1em;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.buttons-row {
  margin-top: 1.5rem;
}

.button-class {
  font-size: 1.25rem;
  /*margin-right: 1.5rem;*/
}

.contact-btn {
  font-size: 1.1rem;
}

.payment-icons {
  justify-content: space-around;
  margin-top: 2rem;
}

.payment-icon {
  height: 60px;
  max-width: 80px;
  margin-right: 20px;
}

/* Small devices (greater than 600px) */
@media (min-width: 601px) {
  /* Your CSS rules for small devices go here */
}

/* Medium devices (greater than 960px) */
@media (min-width: 961px) {
  /* Your CSS rules for medium devices go here */
  .title{
    font-size: 2.5rem;
  }
}

/* Large devices (greater than 1264px) */
@media (min-width: 1265px) {
  .title{
    font-size: 3rem;

  }

  /* Your CSS rules for large devices go here */
}

/* Extra large devices (greater than 1904px) */
@media (min-width: 1905px) {
  /* Your CSS rules for extra large devices go here */
}



@media screen and (min-width: 1920px) {

  .description {
    font-size: 1em;
  }

  .display-2 {
    font-size: 3.5rem; /* Scaled up for desktop */
    line-height: 1.3;
    margin-bottom: 1.5rem;
  }


  .description {
    font-size: 1.5rem;
  }

  .button-class {
    font-size: 1.5rem;
    padding: 1rem 2rem;
  }

  .contact-btn {
    font-size: 1.25rem;
  }

  .payment-icon {
    height: 80px;
    max-width: 100px;
  }
}


/*.display-2 {*/
/*  font-size: 4rem; !* Even bigger for ultra-wide screens *!*/
/*}*/
</style>
