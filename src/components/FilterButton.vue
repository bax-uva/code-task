<template>
  <v-btn @click="categoryClicked" class="pa-0 ma-0" tile outlined
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
