<template>
  <div>
    <v-dialog
      v-if="$store.state.showHeroDialog"
      v-model="$store.state.showHeroDialog"
      width="1000"
    >
      <v-card>
        <v-toolbar color="blue" dark>
          <v-btn icon><v-icon>mdi-close</v-icon></v-btn>
          <v-toolbar-title> Hero information </v-toolbar-title>
        </v-toolbar>
        <v-card-text>
          <v-row class="ma-0 mt-5">
            <v-col md="5">
              <!-- Image -->
              <v-card>
                <v-img
                  height="500"
                  :src="$store.state.selectedHero.images.md"
                />
              </v-card>
            </v-col>
            <v-col
              >
              <!-- Work -->
              <v-card
                ><v-card-text>
                  <v-row class="ma-0 mt-3" justify="start">
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.work.occupation }}
                    </div>
                  </v-row>
                </v-card-text></v-card
              >
              <v-row class="ma-0">
                <v-col>
                  <!-- Name -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div class="blue--text" style="font-size: 1.5em">
                      {{ $store.state.selectedHero.name }}
                    </div>
                  </v-row>
                  <!-- BIOGRAPHY -->
                  <v-row class="ma-0 mt-4" justify="start">
                    <div class="font-weight-bold" style="font-size: 1.2em">
                      Biography
                    </div>
                  </v-row>
                  <v-divider class="mr-14" />
                  <!-- Full name -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Full name:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.biography.fullName }}
                    </div>
                  </v-row>
                  <!-- Gender -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Gender:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.appearance.gender }}
                    </div>
                  </v-row>
                  <!-- Race -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Race:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.appearance.race }}
                    </div>
                  </v-row>
                  <!-- publisher -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Publisher:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.biography.publisher }}
                    </div>
                  </v-row>
                </v-col>
                <v-col>
                  <!-- POWERSTATS -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div class="font-weight-bold" style="font-size: 1.2em">
                      Power Stats
                    </div>
                  </v-row>
                  <v-divider class="mr-14" />
                  <!-- Intelligence -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Intelillence:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.intelligence }}
                    </div>
                  </v-row>
                  <!-- Speed -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Speed:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.speed }}
                    </div>
                  </v-row>
                  <!-- Power -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Power:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.power }}
                    </div>
                  </v-row>
                  <!-- Strength -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Strength:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.strength }}
                    </div>
                  </v-row>
                  <!-- Durability -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Durability:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.durability }}
                    </div>
                  </v-row>
                  <!-- Combat -->
                  <v-row class="ma-0 mt-3" justify="start">
                    <div style="font-size: 1.1em">Combat:</div>
                    <div class="ml-1 font-weight-bold" style="font-size: 1.1em">
                      {{ $store.state.selectedHero.powerstats.combat }}
                    </div>
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>

<script lang="ts">
import mixin from "@/mixin";
import Component, { mixins } from "vue-class-component";

@Component
export default class HeroDialog extends mixins(mixin) {}
</script>