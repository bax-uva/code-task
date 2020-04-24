<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" scrollable>
      <template v-slot:activator="{ on }">
        <v-btn
          color="purple accent-3"
          class="ma-4 pa-2 text-capitalize body-1"
          v-on="on"
          tile
          outlined
          >Add {{ category }}</v-btn
        >
      </template>
      <v-card>
        <v-card-title>
          <span class="headline">Add {{ category }}</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <p class="body-1">Create new item?</p>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="purple accent-3"
            class="body-1"
            tile
            outlined
            @click="dialog = false"
            >Close</v-btn
          >
          <v-btn
            color="purple accent-3"
            class="body-1"
            tile
            outlined
            @click="newItemSaved"
            >Create</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  name: "AddButton",
  props: ["category"],
  data() {
    return {
      dialog: false
    };
  },
  methods: {
    newItemSaved() {
      this.$emit("new-item", this.category);
      this.dialog = false;
    }
  }
};
</script>
