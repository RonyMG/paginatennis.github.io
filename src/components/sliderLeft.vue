<template>
  <Carousel class="carousel__slide--left" :items-to-show="1" :wrap-around="true">
    <Slide v-for="slide in slides" :key="slide">
      <div class="carousel__item">
        <img :src="slide.image" alt="Imagen de bola de Tennis" class="carousel__left-img">
        <div class="carousel__content">
          <h1 class="carousel__h1">
            {{ slide.title }}
            <span class="carousel__span">
              {{ slide.titleBold }}
            </span>
          </h1>
          <p class="carousel__p">
            {{ slide.description }}
          </p>
        </div>
      </div>
    </Slide>

    <template #addons>
      <Pagination />
      <Navigation />
    </template>

  </Carousel>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide, Pagination } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'WrapAround',
  components: {
    Carousel,
    Slide,
    Navigation,
    Pagination
  },
  data: () => ({
    slides: [
      { slide: 1, title: 'Nuestras', titleBold: 'Raquetas', description: 'Conoce nuestras raquetas y aprende a usar Tennis cómo un profesional', image:'images/bola-tenis.png'},
      { slide: 2, title: 'Tus mejores', titleBold: 'Raquetas Favoritas', description: 'Desarrolla tus habilidades con la mejor tecnología en raquetas de Tennis', image:'images/bola-tenis-2.jpeg' },
      { slide: 3, title: 'Las', titleBold: 'Raquetas', description: 'Conoce nuestras raquetas y aprende a usar Tennis cómo un profesional', image:'images/bola-tenis.png' },
      { slide: 4, title: 'Mejor', titleBold: 'Tecnología', description: 'Desarrolla tus habilidades con la mejor tecnología en raquetas de Tennis lorem impsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum', image:'images/bola-tenis-2.jpeg' }
    ]
  })
})
</script>

<style lang="scss">
/*Estilos default de vue3-carousel*/
.carousel__item {
  min-height: 200px;
  width: 100%;
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid var(--white);
}
</style>
