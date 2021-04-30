<template>
    <home-component />
</template>

<script lang="ts">
  import Vue from 'vue'
  import HomeComponent from '../components/HomeComponent.vue'

  export default Vue.extend({
    name: 'Home',

    data: () => ({
      gameDatas: {
        currentLevel: 0,
        keyPossesed: [],
      }
    }),

    components: {
      HomeComponent,
    },
  })
</script>
