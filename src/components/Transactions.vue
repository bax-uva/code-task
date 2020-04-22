<template>
  <v-card style="border:1px solid black;" tile outlined>
    <v-card-title style="border-bottom:1px solid black;">{{
      category
    }}</v-card-title>
    <ListItem
      v-for="(item, index) in filteredItems"
      :item="item.id"
      :index="index"
      :cat="item.category"
      v-bind:key="item.id"
    />
    <v-card-actions>
      <AddButton />
      <ShowAllButton />
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
  }
};
</script>
