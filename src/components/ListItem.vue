<template>
  <v-list-item class="ma-0">
    <v-list-item-content>
      <v-list-item-title class="body-1"
        ><span class="text-capitalize">{{ catSingular }}</span> #{{
          item.substr(item.length - 5, item.length)
        }}</v-list-item-title
      >
    </v-list-item-content>
  </v-list-item>
</template>

<script>
export default {
  name: "ListItem",
  props: ["item", "cat"],
  computed: {
    catSingular() {
      let cat = this.cat;
      return cat.substr(0, cat.length - 1);
    }
  }
};
</script>
