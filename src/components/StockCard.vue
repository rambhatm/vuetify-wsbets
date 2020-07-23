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
      <v-btn smarr color="primary" @click="trade">Buy</v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-if="showBuyOptions">
        <v-col class="shrink">
          <v-subheader class="pl-0">How many stocks do you want ?</v-subheader>
          <v-slider v-model="slider" :thumb-size="24" thumb-label="always">
            <template
              v-slot:thumb-label="{ value }"
            >{{ satisfactionEmojis[Math.min(Math.floor(value / 10), 9)] }}</template>
          </v-slider>
        </v-col>
      </div>
    </v-expand-transition>
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
      satisfactionEmojis: [
        "😭",
        "😢",
        "☹️",
        "🙁",
        "😐",
        "🙂",
        "😊",
        "😁",
        "😄",
        "😍"
      ],
      loading: false,
      selection: 1,
      slider: 0,
      showBuyOptions: false
    };
  },
  methods: {
    trade() {
      this.loading = true;
      this.showBuyOptions = !this.showBuyOptions;
      setTimeout(() => (this.loading = false), 2000);
    }
  }
};
</script>