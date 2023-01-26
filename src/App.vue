
<template>
    

    <navbar />
    <mainBanner />
    <section class="second-banner">
      <div class="second-banner__child">
        <span class="second-banner__span">Tennis</span>
      </div>
      <div class="second-banner__child">
        <h1 class="second-banner__h1">Raquetas.Accesorios.Pelotas</h1>
        <p class="second-banner__p">Conoce nuestras raquetas y aprende a jugar Tennis cómo un profesional.</p>
      </div>
      <div class="second-banner__child">
        <button class="main-button invert">Historia</button>
      </div>
    </section>
    <section class="sliders-grid__section">
      <div class="sliders-grid__left"><sliderLeft /></div>
      <div class="sliders-grid__right"><sliderRight /></div>
    </section>
    <section class="bg-section">
    </section>
    <fooTer ></fooTer>
</template>

<script setup>
import navbar from './components/navbar.vue'
import mainBanner from './components/mainBanner.vue'
import sliderLeft from './components/sliderLeft.vue'
import sliderRight from './components/sliderRight.vue'
import fooTer from './components/fooTer.vue'
</script>

<style scoped>

</style>
