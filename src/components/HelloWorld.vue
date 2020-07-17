<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img :src="require('../assets/wsb_logo.png')" class="my-3" contain height="100" />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">Welcome to Wall Street Bets!</h1>
      </v-col>
    </v-row>

    <v-row>
      <v-col class="mb-4">
        <stocksearch></stocksearch>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import stocksearch from "./StockSearch";
export default {
  name: "HelloWorld",

  data: () => ({}),
  components: {
    stocksearch
  }
};
</script>
