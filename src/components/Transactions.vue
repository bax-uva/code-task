<template>
  <v-card class="mx-auto" max-width="344" outlined>
    <v-card-title>Transactions type</v-card-title>
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
