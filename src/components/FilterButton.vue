<template>
  <v-btn class="pa-0 ma-0" tile outlined>{{ title }} </v-btn>
</template>

<script>
export default {
  name: "FilterButton",
  props: ["title"]
};
</script>
