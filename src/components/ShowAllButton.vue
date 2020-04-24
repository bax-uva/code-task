<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" scrollable>
      <template v-slot:activator="{ on }">
        <v-btn
          outlined
          color="purple accent-3"
          class="ma-4 pa-2 text-capitalize body-1"
          tile
          v-on="on"
          >Show All</v-btn
        >
      </template>
      <v-card>
        <v-card-title class="text-capitalize">{{ category }}</v-card-title>
        <v-divider></v-divider>
        <v-card-text style="height: 300px;">
          <ListItem
            v-for="item in filteredItems"
            :item="item.id"
            :cat="item.category"
            v-bind:key="item.id"
          />
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn
            color="purple accent-3"
            class="ma-2"
            tile
            outlined
            @click="dialog = false"
            >Close</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
import ListItem from "./ListItem";

export default {
  name: "ShowAllButton",
  components: {
    ListItem
  },
  props: ["category", "filteredItems"],
  data() {
    return {
      dialog: false
    };
  }
};
</script>
