<template>
  <div class="mx-2 my-2">
      <v-card outlined @click="onShowDialog()">
          <v-card-text>
              <!-- Image -->
              <v-img height="300"  :src="heroData.images.md" />
              <!-- Name -->
              <v-row class="ma-0 mt-3" justify="center">
                  <div class="blue--text" style="font-size:1.5em">{{heroData.name}}</div>
              </v-row>
              <!-- Intelligence -->
              <v-row class="ma-0 mt-3" justify="start">
                  <div  style="font-size:1.1em">Intelillence: </div>
                  <div class="ml-1 font-weight-bold" style="font-size:1.1em">{{heroData.powerstats.intelligence}}</div>
              </v-row>
              <!-- Speed -->
              <v-row class="ma-0 mt-1" justify="start">
                  <div  style="font-size:1.1em">Speed: </div>
                  <div class="ml-1 font-weight-bold" style="font-size:1.1em">{{heroData.powerstats.speed}}</div>
              </v-row>
              <!-- Power -->
              <v-row class="ma-0 mt-1" justify="start">
                  <div  style="font-size:1.1em">Power: </div>
                  <div class="ml-1 font-weight-bold" style="font-size:1.1em">{{heroData.powerstats.power}}</div>
              </v-row>
              <!-- Gender -->
              <v-row class="ma-0 mt-1" justify="start">
                  <div  style="font-size:1.1em">Gender: </div>
                  <div class="ml-1 font-weight-bold" style="font-size:1.1em">{{heroData.appearance.gender}}</div>
              </v-row>
              <!-- Race -->
              <v-row class="ma-0 mt-1" justify="start">
                  <div  style="font-size:1.1em">Race: </div>
                  <div class="ml-1 font-weight-bold" style="font-size:1.1em">{{heroData.appearance.race}}</div>
              </v-row>
          </v-card-text>
      </v-card>
  </div>
</template>

<script lang="ts">
import mixin from "@/mixin";
import Component, { mixins } from "vue-class-component";
import { Prop } from "vue-property-decorator";
import axios from "axios";

@Component
export default class HeroCard extends mixins(mixin) {
  @Prop() heroData: any;

  mounted(){
      console.log(this.heroData);
  }

  onShowDialog(){
      this.$store.state.selectedHero = this.heroData;
      this.$store.state.showHeroDialog = true;
  }
}
</script>