<template>
  <v-card :loading="loading" class="mx-auto my-12" max-width="374">
    <v-img height="250" :src="stock.Image"></v-img>

    <v-card-title>{{stock.Symbol}}</v-card-title>

    <v-card-text>
      <div class="my-4 subtitle-4">{{stock.Name}}</div>

      <div>A company</div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-text>
      <v-chip-group column>
        <v-chip class="ma-2" color="orange" text-color="white">
          {{stock.Industry}}
          <v-icon left>mdi-computer</v-icon>
        </v-chip>
        <v-chip class="ma-2" color="orange" text-color="white">
          {{stock.Sector}}
          <v-icon left>mdi-computer</v-icon>
        </v-chip>
      </v-chip-group>
    </v-card-text>

    <v-card-actions>
      <v-btn color="deep-purple lighten-2" text @click="trade">Reserve</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "stockcard",
  props: {
    stock: {
      type: Object,
      description: "stock data returned from api"
    }
  },
  data() {
    return {
      loading: false,
      selection: 1
    };
  },
  methods: {
    trade() {
      this.loading = true;
      setTimeout(() => (this.loading = false), 2000);
    }
  }
};
</script>