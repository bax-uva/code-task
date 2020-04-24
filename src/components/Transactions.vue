<template>
  <v-card elevation="10" min-width="250" tile outlined class="ma-4">
    <v-card-title class="text-capitalize title">{{ category }}</v-card-title>
    <v-divider></v-divider>
    <ListItem
      v-for="item in filteredItems.slice(0, 3)"
      :item="item.id"
      :cat="item.category"
      v-bind:key="item.id"
    />
    <v-card-actions>
      <AddButton :category="category" @new-item="getSavedItem" />
      <ShowAllButton :category="category" :filteredItems="filteredItems" />
    </v-card-actions>
  </v-card>
</template>

<script>
import ListItem from "./ListItem";
import AddButton from "./AddButton";
import ShowAllButton from "./ShowAllButton";

export default {
  name: "Transactions",
  components: {
    ListItem,
    AddButton,
    ShowAllButton
  },
  props: ["category", "items"],
  computed: {
    filteredItems() {
      return this.items.filter(a => a.category == this.category);
    }
  },
  methods: {
    getSavedItem(category) {
      this.$emit("new-item", category);
    }
  }
};
</script>
