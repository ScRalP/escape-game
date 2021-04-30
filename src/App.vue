<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <router-link
        to="/"
        tag="v-btn"
      >
        <v-btn
          color="blue"
          block
          value="feed"
        >
          <v-icon color="white">mdi-home</v-icon>
        </v-btn>
      </router-link>
     
      <timer class="Timer" />

      <router-link
        to="/puzzle"
        tag="v-btn"
      >
        <v-btn
          color="blue"
          block
          value="feed"
        >
          <v-icon color="white">mdi-puzzle</v-icon>
        </v-btn>
      </router-link>
    </v-app-bar>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Timer from './components/Timer.vue'

export default Vue.extend({
  name: 'App',

  components: {
    Timer,
  },
});
</script>


<style>
@font-face {
  font-family: "Digit";
  src: url("./assets/fonts/Digit.TTF");
}
</style>