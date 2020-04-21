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
      <FilterButton />
      <FilterButton />
      <FilterButton />
      <FilterButton />
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
  }
};
</script>
