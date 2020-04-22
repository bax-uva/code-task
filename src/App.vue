<template>
  <v-app>
    <Header :categories="categories" @category-filter="updateCategory" />
    <v-content class="d-flex align-center">
      <v-container class="d-flex justify-space-around align-center">
        <Transactions
          v-show="chosenFilter == category"
          v-bind:key="category"
          v-for="category in categories"
          :category="category"
          :items="items"
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
      categories: []
    };
  },
  methods: {
    extractCategories() {
      this.categories = items
        .map(a => a.category)
        .filter((a, b, c) => c.indexOf(a) == b);
    },
    updateCategory(currCategory) {
      this.chosenFilter = currCategory;
    }
  },
  created() {
    this.extractCategories();
  }
};
</script>
