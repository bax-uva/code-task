<template>
  <v-app-bar
    flat
    class="header ma-0 pa-0 d-flex flex-row justify-space-around align-center"
    style="background-color: white; border-bottom: 1px solid black;"
  >
    <v-img
      alt="Logo"
      contain
      src="https://source.unsplash.com/kxkXVlNL7H0/1000"
      width="40"
    />
    <v-container class="filter-menu d-flex justify-center pa-0">
      <FilterButton :title="'All'" />
      <FilterButton
        v-for="category in extractedCategories"
        v-bind:key="category"
        :title="category"
      />
    </v-container>
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
  props: ["items"],
  computed: {
    extractedCategories() {
      return this.items
        .map(a => a.category)
        .filter((a, b, c) => c.indexOf(a) == b);
    }
  }
};
</script>
