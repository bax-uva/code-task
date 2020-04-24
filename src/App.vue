<template>
  <v-app class="d-flex">
    <Header
      :chosenFilter="chosenFilter"
      :categories="categories"
      @category-filter="updateCategory"
    />
    <v-content class="d-flex align-center">
      <v-container
        class="d-flex flex-column flex-sm-row justify-space-around align-center"
      >
        <Transactions
          v-show="chosenFilter == category || chosenFilter == 'all'"
          v-bind:key="category"
          v-for="category in categories"
          :category="category"
          :items="items"
          @new-item="addItem"
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
    },
    generateRandomId() {
      let randomId = "";
      const characters = "abcdefghijklmnopqrstuvwxyz0123456789";
      const idLength = 24;
      for (let i = 0; i < idLength; i++) {
        let randomChar =
          characters[Math.floor(Math.random() * characters.length)];
        randomId += randomChar;
      }
      return randomId;
    },
    addItem(category) {
      let newItem = {
        id: this.generateRandomId(),
        category: category
      };
      this.items.push(newItem);
    }
  },
  created() {
    this.extractCategories();
  }
};
</script>
