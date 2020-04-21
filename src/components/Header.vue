<template>
  <v-app-bar class="d-flex justify-md-space-between dark dense">
    <v-img
      alt="Logo"
      contain
      src="https://source.unsplash.com/kxkXVlNL7H0/1000"
      transition="scale-transition"
      width="40"
    />
    <div class="filter-bar">
      <FilterButton />
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
  }
};
</script>
