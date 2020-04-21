<template>
  <v-app>
    <Header :items="items" />
    <v-content class="d-flex align-center">
      <v-container class="d-flex justify-space-around align-center">
        <Transactions />
        <Transactions />
        <Transactions />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Header from "./components/Header";
import Transactions from "./components/Transactions";
import items from "./data/data.json";

export default {
  name: "App",
  components: {
    Header,
    Transactions
  },
  data: () => ({
    items
  })
};
</script>
