<template>
  <v-btn class="ma-2" tile outlined>Add {{ category }}</v-btn>
</template>

<script>
export default {
  name: "AddButton",
  props: ["category"]
};
</script>
