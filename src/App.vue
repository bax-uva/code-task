<template>
  <v-app>
    <Header />
    <v-content>
      <Transactions />
    </v-content>
  </v-app>
</template>

<script>
import Header from "./components/Header";
import Transactions from "./components/Transactions";

export default {
  name: "App",

  components: {
    Header,
    Transactions
  },

  data: () => ({
    //
  })
};
</script>
