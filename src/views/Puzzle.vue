<template>
    <puzzle-component />
</template>

<script lang="ts">
  import Vue from 'vue'
  import PuzzleComponent from '../components/PuzzleComponent.vue'

  export default Vue.extend({
    name: 'Puzzle',

    components: {
      PuzzleComponent,
    },
  })
</script>
