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
          setWrapperSize: true,
          on: {
            slideChange (swiper) {
              if(swiper.realIndex == 1){
                document.body.classList.add('beige-theme')
              } else {
                document.body.classList.remove('beige-theme')
              }

              if(swiper.realIndex == 2){
                document.body.classList.add('blue-theme')
              } else {
                document.body.classList.remove('blue-theme')
              }

              if(swiper.realIndex == 3){
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