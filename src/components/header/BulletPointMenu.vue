<template>
  <div>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-list-item
            rounded="xl"
            v-bind="attrs"
            v-on="on"
        >
          <v-list-item-content>
            <v-list-item-title>{{ title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </template>

      <!-- Sub-items dropdown list -->
      <v-list>
        <v-list-item
            v-for="(subItem, index) in subItems"
            :key="index"
            @click="handleSubItemClick(subItem.href)"
        >
          <v-list-item-content>
            <v-list-item-title>{{ subItem.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "BulletPointMenu",
  props: {
    title: {
      type: String,
      required: true,
    },
    subItems: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleSubItemClick(href) {
      this.$emit('item-click', href); // Emit event to parent component
    }
  }
}
</script>