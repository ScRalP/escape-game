<template>
  <v-carousel>
    <v-carousel-item
      v-for="(text, i) in texts"
      :key="text"
    >
      <v-sheet
        class="CarouselSlide"
        color="gray"
        tile
      >
        <v-img
          v-bind:src="require('@' + '/assets/images/' + images[i] +'.png')"
          class="CarouselSlide-RickImage"
          contain
        ></v-img>
        <p class="CarouselSlide-Text mt-3">
          {{ text }}
        </p>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'HomeComponent',

  data: () => ({
    texts: [
      "Morty you got to help me!...",
      "MY PORTAL GUN HAVE NO CHARGE LEFT!!!!",
      "You have to find a solution Morty, you know only you can do it... Because you're so special...",
      "Here, take this. It's a note I wrote for myself hours ago. Too bad I don't remember why.",
      "And don't touch anything that have more than 3 legs!!",
    ],
    images: [
      "rick_1",
      "rick_2",
      "retarded_rick",
      "rick_1",
      "rick_2",
    ]
  }),
})
</script>

<style lang="scss">
.CarouselSlide{
  height: 100%;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;

  &-RickImage{
    width: 200px;
  }

  &-Text{
    padding-right: 80px;
    padding-left: 80px;
    text-align: center;
    word-break: normal;
  }
  
}
</style>