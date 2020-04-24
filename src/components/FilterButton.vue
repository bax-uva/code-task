<template>
  <v-btn
    outlined
    color="purple accent-3"
    tile
    @click="categoryClicked"
    class="pa-2 ma-0 text-capitalize body-1"
    >{{ title }}
  </v-btn>
</template>

<script>
export default {
  name: "FilterButton",
  props: ["title"],
  methods: {
    categoryClicked() {
      this.$emit("category-clicked", this.title);
    }
  }
};
</script>
