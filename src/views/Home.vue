<template>
  <div>
    <div class="mt-10">
      <v-data-iterator
        :items="herosList"
        :items-per-page="10"
        :page="page"
        :search="search"
        class="pb-10 mb-10"
        style="margin-left: 200px !important; margin-right: 200px !important;"
      >
      <!-- Search bar -->
        <template v-slot:header>
          <v-row justify="center" class="mt-0">
            <v-col md="6" cols="12" align="center">
              <v-text-field
                dense
                v-model="search"
                clearable
                outlined
                label="Buscar personaje"
              />
            </v-col>
          </v-row>
        </template>

      <!-- Items grids -->
        <template v-slot:default="props">
          <v-row class="ma-0 mt-10">
            <v-col
              v-for="(hero, index) in props.items"
              :key="index"
              cols="12"
              lg="3"
              md="3"
              sm="12"
              class="ma-0 pa-0"
            >
              <HeroCard :heroData="hero" />
            </v-col>
          </v-row>
        </template>
      </v-data-iterator>
    </div>
    <HeroDialog  />
  </div>
</template>

<script lang="ts">
import mixin from "@/mixin";
import Component, { mixins } from "vue-class-component";
import axios from "axios";
import HeroCard from "@/components/HeroCard.vue";
import HeroDialog from "@/components/HeroDialog.vue";

@Component({
  components:{
    HeroCard,
    HeroDialog
  }
})
export default class Home extends mixins(mixin) {
  search = "";
  page = 1;
  text = "Hola mundo";
  herosList: Array<any> = [];

  mounted() {
    this.post();
  }

  async post() {
    const resp = await axios.get(
      "https://akabab.github.io/superhero-api/api/all.json"
    );
    this.herosList = resp.data;
  }
}
</script>

<style>
/* .row{
  margin-left: 200px;
} */
</style>
