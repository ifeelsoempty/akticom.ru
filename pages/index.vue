<template>
  <div v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__subtitle">
              Akticom - это digital-студия
            </div>
            <div class="slide__title">
              Решаем digital задачи
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__subtitle">
              Проектируем крутые сайты
            </div>
            <div class="slide__title">
              Решаем digital задачи
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__subtitle">
              Проектируем крутые сайты
            </div>
            <div class="slide__title">
              Решаем digital задачи
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__subtitle">
              Проектируем крутые сайты
            </div>
            <div class="slide__title">
              Решаем digital задачи
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'

import 'swiper/swiper-bundle.css'

  export default {
    components: {
      Swiper,
      SwiperSlide
    },
    directives: {
      swiper: directive
    },
    data() {
      return {
        swiperOption: {
          notNextTick: true,
          on: {
            progress (swiper) {
              let progress = swiper.progress;
              let slideStep = 1 / (swiper.slides.length - 1);

              if((progress > (slideStep / 2)) && (progress <= slideStep + (slideStep / 2))){
                document.body.classList.add('beige-theme')
              } else {
                document.body.classList.remove('beige-theme')
              }

              if((progress > slideStep + (slideStep / 2)) && (progress <= ((slideStep * 2) + (slideStep / 2)))){
                document.body.classList.add('blue-theme')
              } else {
                document.body.classList.remove('blue-theme')
              }

              if((progress > ((slideStep * 2) + (slideStep / 2)))){
                document.body.classList.add('purple-theme')
              } else {
                document.body.classList.remove('purple-theme')
              }

            }
          }
        }
      }
    },
    mounted() {
    }
  }
</script>

<style>
.swiper-wrapper{
  width: 100vw;
  height: 100vh;
}
</style>