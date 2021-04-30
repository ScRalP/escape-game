<template>
  <v-container class="Container">
    <v-img
      src="../assets/images/portal_gun.png"
      contain
    />

    <v-row class="Container-Row">
      <v-dialog
        v-model="dialog"
        width="500"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="grey darken-2"
            dark
            v-bind="attrs"
            v-on="on"
          >
            <v-icon color="white">mdi-file</v-icon>
          </v-btn>
        </template>

        <v-card>
          <v-card-text>
            <p>.nwod edispu em ees ylno nac uoY</p>
            <!-- <p>.em ees nac uoy krad eht ni ylnO</p> -->
            <p>.htap eht wolloF</p>
          </v-card-text>
  
          <v-divider></v-divider>
  
          <v-card-text
            class="Signature"
          >
            Rick Sanchez
          </v-card-text>
        </v-card>
      </v-dialog>

      <v-dialog
        v-model="dialog"
        width="500"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="grey darken-2"
            dark
            v-bind="attrs"
            v-on="on"
          >
            <v-icon color="white">mdi-map</v-icon>
          </v-btn>
        </template>

        

        <v-card>
          <v-img
            :src="this.isUpsideDown ? require('@/assets/images/treasure_map.png'): require('@/assets/images/treasure_map_revealed.png')"
            :key="this.isUpsideDown"
            class="TreasureMap"
          >
          </v-img>
        </v-card>
      </v-dialog>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'PuzzleComponent',

  mounted() {
    window.screen.orientation.addEventListener('change', ()=>{
      if(window.screen.orientation.type === 'portrait-secondary' || window.screen.orientation.type === 'landscape-secondary' ){
        this.isUpsideDown = false;
      } else{
        this.isUpsideDown = true;
      }
    });
  },
  data: () => ({
    isUpsideDown: true,
  }),
})
</script>

<style lang="scss" scoped>
.TreasureMap{
  transition: 300ms;
}

.Signature{
  width: 100%;
  text-align: right;
  font-style: italic;
  font-size: 18px;
}

.Container{
  height: 100%;
  display: flex;
  flex-direction: column;

  &-Row{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
  }
}

</style>
