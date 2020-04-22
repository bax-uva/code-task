<template>
  <v-list-item three-line>
    <v-list-item-content>
      <v-list-item-title class="headline mb-1"
        >{{ catSingular }} #{{
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
