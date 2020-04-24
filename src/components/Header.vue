<template>
  <v-app-bar
    color="white"
    class="header ma-0 pa-0 d-flex justify-space-around align-center"
  >
    <v-img
      class="ma-4"
      alt="Logo"
      contain
      src="https://source.unsplash.com/kxkXVlNL7H0/1000x1000"
      width="50"
      style="border-radius: 100%;"
    />

    <div class="filter-menu d-flex pa-0 ma-4">
      <FilterButton :title="'all'" @category-clicked="updateCategory" />
      <FilterButton
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
  props: ["categories"],
  methods: {
    updateCategory(category) {
      this.$emit("category-filter", category);
    }
  }
};
</script>
