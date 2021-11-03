<template>
  <v-app>
    <v-app-bar
      app
      color="grey lighten-3"
      height="120"
      flat
    >
      <v-row class="ma-0">
        <v-col class="ml-10">
          <img class="ml-10" alt="Vue logo" src="@/assets/Logo.png" />
        </v-col>
        <v-col md="5" align-self="center">
          <v-row justify="space-around" align="center">
            <p>Item 1</p>
            <p>Item 2</p>
            <p>Item 3</p>
          </v-row>
        </v-col>
      </v-row>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  data: () => ({
    //
  }),
});
</script>
