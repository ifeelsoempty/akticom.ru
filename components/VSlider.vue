<template>
  <div class="v-slider" @slideChange="onSlideChange" v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div class="swiper-slide slide">
        <HSlider v-bind:isActive = "activeSlide === 1 ? true : false"/>
      </div>
      <div class="swiper-slide slide">
        <WorkSlider v-bind:isActive = "activeSlide === 2 ? true : false"/>
      </div>
    </div>
    <div class="slider-static container">
      <div class="slider-mouse">
        <svg width="34px" height="50px" viewBox="0 0 247 390" fill="none" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
          <path class="slider-mouse__wheel" d="M123.359,79.775l0,72.843" stroke="#F2EFE8" stroke-width="15"/>
          <path d="M236.717,123.359c0,-62.565 -50.794,-113.359 -113.358,-113.359c-62.565,0 -113.359,50.794 -113.359,113.359l0,143.237c0,62.565 50.794,113.359 113.359,113.359c62.564,0 113.358,-50.794 113.358,-113.359l0,-143.237Z" stroke="#F2EFE8" stroke-width="15"/>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
import { directive } from 'vue-awesome-swiper'

import 'swiper/swiper-bundle.css'

export default {
  directives: {
    swiper: directive
  },
  data() {
    return {
      activeSlide: 1,
      swiperOption: {
        direction: 'vertical',
        allowTouchMove: false,
        spaceBetween: 100,
        speed: 1000,
        mousewheelControl: true,
        on: {
          init(swiper) {
            const content = document.querySelector('.v-slider');

            let delay = false;
            content.addEventListener("wheel" , (e) => {
              if(!delay){
                e.deltaY < 0 ? swiper.slidePrev() : swiper.slideNext();
                delay = true;

                setTimeout(() => {
                  delay = false;
                }, 525)
              }
            });
          },
          progress (swiper) {
            let progress = swiper.progress;
            let slideStep = 1 / (swiper.slides.length - 1);
            let halfSlideStep = slideStep / 2;

            const hSlider = document.querySelector('.h-slider');

            if(progress <= halfSlideStep){
              let themeClass = hSlider.dataset.theme;
              if(themeClass && themeClass != 'default-theme'){
                document.body.classList.add(hSlider.dataset.theme)
              }
            } else {
              document.body.classList.remove(hSlider.dataset.theme);
            }
          },
        }
      }
    }
  },
  methods: {
    onSlideChange: function (swiper) {
      this.activeSlide = swiper.realIndex + 1;
    }
  }
}
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>