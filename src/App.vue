<template>
  <v-app>
    <v-app-bar app color="green accent-3" dark>
      <div class="d-flex align-center">
        <v-img
          alt="wsb logo"
          class="shrink mr-2"
          contain
          src="./assets/wsb_logo.png"
          min-width="100"
          transition="scale-transition"
          width="200"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank" text>
        <span class="mr-2">Login with Reddit!</span>
        <v-icon>mdi-login</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data: () => ({
    //
  })
};
</script>
