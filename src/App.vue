<template>
  <v-app>
    <Header :items="items" @category-filter="updateCategory" />
    <v-content class="d-flex align-center">
      <v-container class="d-flex justify-space-around align-center">
        <Transactions v-show="chosenFilter == 'offers'" :category="'offers'" />
        <Transactions
          v-show="chosenFilter == 'incomes'"
          :category="'incomes'"
        />
        <Transactions
          v-show="chosenFilter == 'outcomes'"
          :category="'outcomes'"
        />
        <Transactions
          v-show="chosenFilter == 'all'"
          v-bind:key="category"
          v-for="category in categories"
          :category="category"
        />
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
  data: () => {
    return {
      items,
      chosenFilter: " ",
      categories: ["offers", "incomes", "outcomes"]
    };
  },
  methods: {
    updateCategory(currCategory) {
      this.chosenFilter = currCategory;
    }
  }
};
</script>
