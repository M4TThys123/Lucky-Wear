<template>
  <div class="voordelen-wrapper my-md-10"></div>
  <v-container >
    <v-row class="my-4">
      <v-col cols="12" md="4" class="d-flex align-start">
        <div class="ml-3">
          <div class="d-flex align-items-center">
            <v-icon color="blue" size="36px" class="icon-title">mdi-lingerie</v-icon>
            <h3 class="font-weight-bold ml-3">Premium Ondergoed</h3>
          </div>
          <p>Elke maand hoogwaardig ondergoed en lingerie thuis. Probeer je eerste setje gratis!</p>
        </div>
      </v-col>
      <v-col cols="12" md="4" class="d-flex align-start">
        <div class="ml-3">
          <div class="d-flex align-items-center">
            <v-icon color="blue" size="36px">mdi-calendar-sync-outline</v-icon>
            <h3 class="font-weight-bold ml-3">Abonnementsservice</h3>
          </div>
          <p>Eerste set gratis, daarna maandelijks nieuw ondergoed voor een betaalbare prijs. Maandelijks opzegbaar!</p>
        </div>
      </v-col>
      <v-col cols="12" md="4" class="d-flex align-start">
        <div class="ml-3">
          <div class="d-flex align-items-center">
            <v-icon color="blue" size="36px">mdi-texture</v-icon>
            <h3 class="font-weight-bold ml-3">Hoogwaardige Materialen</h3>
          </div>
          <p>Gemaakt van 95% katoen en 5% spandex voor ultiem comfort en duurzaamheid. Antibacterieel en ademend!</p>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'VoordelenSection',
};
</script>

<style scoped>
.font-weight-bold {
  font-size: 1.25rem;
}
.icon-title {
  margin-right: 8px;
}
.voordelen-wrapper{
  width: 100%;
  background: var(--color-background-grey)
}
</style>
