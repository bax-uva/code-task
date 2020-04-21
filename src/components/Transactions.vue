<template>
  <v-card style="border:1px solid black;" tile outlined>
    <v-card-title style="border-bottom:1px solid black;"
      >Transactions type</v-card-title
    >
    <ItemList />
    <v-card-actions>
      <AddButton />
      <ShowAllButton />
    </v-card-actions>
  </v-card>
</template>

<script>
import ItemList from "./ItemList";
import AddButton from "./AddButton";
import ShowAllButton from "./ShowAllButton";

export default {
  name: "Transactions",
  components: {
    ItemList,
    AddButton,
    ShowAllButton
  }
};
</script>
