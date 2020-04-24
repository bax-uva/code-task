<template>
  <v-app-bar
    color="white"
    class="header ma-0 pa-0 d-flex justify-space-around align-center"
  >
    <v-img
      class="ma-4"
      alt="Logo"
      contain
      src="../assets/logo.png"
      width="50"
      style="border-radius: 100%;"
    />

    <div class="filter-menu d-flex pa-0 ma-4">
      <FilterButton
        :title="'all'"
        @category-clicked="updateCategory"
        :chosenFilter="chosenFilter"
      />
      <FilterButton
        :chosenFilter="chosenFilter"
        v-for="category in categories"
        v-bind:key="category"
        :title="category"
        @category-clicked="updateCategory"
      />
    </div>
    <Search />
  </v-app-bar>
</template>
<script>
import FilterButton from "./FilterButton";
import Search from "./Search";

export default {
  name: "Header",
  components: {
    FilterButton,
    Search
  },
  props: ["categories", "chosenFilter"],
  methods: {
    updateCategory(category) {
      this.$emit("category-filter", category);
    }
  }
};
</script>
