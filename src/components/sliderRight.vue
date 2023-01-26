<template>
  <Carousel class="carousel__slide--right" :settings="settings" :breakpoints="breakpoints">
    <Slide v-for="slide in slides" :key="slide">
      <div class="carousel__item">
        <div class="carousel__count" v-if="slide.count!=null">{{ slide.count }}</div>
        <img :src="slide.image" alt="Imagen de Raqueta de Tennis" class="carousel__right-img" v-if="slide.count!=null">
      </div>
    </Slide>

  </Carousel>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'Breakpoints',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data: () => ({
    slides: [
      { count: 1, image: 'images/group-10.png'},
      { count: 2, image: 'images/group-10.png'},
      { count: 3, image: 'images/group-10.png'},
      { count: 4, image: 'images/group-10.png'},
      { count: 5, image: 'images/group-10.png'},
      { count: 6, image: 'images/group-10.png'},
      { count: null, image: null}
    ],
    // carousel settings
    settings: {
      itemsToShow: 2,
      snapAlign: 'center',
    },
    // breakpoints mobile first
    breakpoints: {
      // 768 and up
      768: {
        itemsToShow: 2,
        snapAlign: 'center',
      },
      // 700px and up
      991: {
        itemsToShow: 2.7,
        snapAlign: 'center',
      },
    },
  }),
})
</script>

<style scoped lang="scss">


</style>