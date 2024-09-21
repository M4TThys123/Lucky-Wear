<template>
  <div class="voordelen-wrapper my-md-10">
    <v-container>
      <v-row class="my-4">
        <v-col
            v-for="(item, index) in voordelen"
            :key="index"
            cols="12"
            md="4"
            class="d-flex align-start"
        >
          <div class="ml-3 ml-md-0">
            <div class="d-flex align-items-center">
              <v-icon :color="item.iconColor" :size="item.iconSize">{{ item.icon }}</v-icon>
              <h3 class="font-weight-bold ml-3">{{ item.title }}</h3>
            </div>
            <p class="pt-3">{{ item.description }}</p>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'VoordelenSection',
  data() {
    return {
      voordelen: [
        {
          icon: 'mdi-lingerie',
          title: 'Premium Ondergoed',
          description: 'Elke maand hoogwaardig ondergoed en lingerie thuis. Probeer je eerste setje gratis!',
          iconColor: 'blue',
          iconSize: '36px',
        },
        {
          icon: 'mdi-calendar-sync-outline',
          title: 'Abonnementsservice',
          description: 'Eerste set gratis, daarna maandelijks nieuw ondergoed voor een betaalbare prijs. Maandelijks opzegbaar!',
          iconColor: 'blue',
          iconSize: '36px',
        },
        {
          icon: 'mdi-texture',
          title: 'Hoogwaardige Materialen',
          description: 'Gemaakt van 95% katoen en 5% spandex voor ultiem comfort en duurzaamheid. Antibacterieel en ademend!',
          iconColor: 'blue',
          iconSize: '36px',
        },
      ],
    };
  },
};
</script>

<style scoped>
.voordelen-title {
  font-size: 1.25rem;
}
.icon-title {
  margin-right: 8px;
}
.voordelen-wrapper {
  width: 100%;
  background: var(--color-background-grey);
}
</style>
