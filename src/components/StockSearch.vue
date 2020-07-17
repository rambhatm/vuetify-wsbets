<template>
  <v-container>
    <v-row>
      <v-col class="mb-4">
        <v-form @submit="doSearch">
          <v-text-field v-model="query" label="Search">
            <v-icon style="vertical-align: middle">mdi-search</v-icon>
          </v-text-field>
        </v-form>
      </v-col>
    </v-row>

    <stockcard v-if="result" :stock="this.result"></stockcard>
  </v-container>
</template>
<script>
import stockcard from "./StockCard";
import axios from "axios";
export default {
  name: "stocksearch",
  data() {
    return {
      query: "",
      result: null
    };
  },
  components: {
    stockcard
  },
  methods: {
    doSearch() {
      //let self = this;
      axios
        .get(`/api/stock/search?query=${this.query}`)
        .then(response => {
          //self.$set(this, "result", response.data);
          this.result = response.data;
        })
        .catch(err => {
          err.stack;
        });
    }
  }
};
</script>