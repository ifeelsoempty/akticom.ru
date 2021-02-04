<template>
  <div class="v-slider" 
      v-swiper:swiper="swiperOption"
      @slideChange="onSlideChange"
    >
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
      }
    }
  },
  watch: {
    activeSlide: function (activeSlide){
      const hSlider = document.querySelector('.h-slider__swiper');

      if(activeSlide === 1){
        document.body.classList.add(hSlider.dataset.theme)
      } else {
        document.body.classList.remove(hSlider.dataset.theme);
      }
    },
  },
  methods: {
    onSlideChange: function (swiper) {
      this.activeSlide = swiper.realIndex + 1;
    },
    onInit: function (swiper) {
      const content = document.querySelector('.v-slider');

      let delay = false;
      content.addEventListener("wheel" , (e) => {
        if(!delay){
          // Call activeSlide watcher before actual slide change to wait until slide animation is end
          if(e.deltaY < 0){
            if(swiper.realIndex === 1){
              this.activeSlide = 0;
              setTimeout(() => {
                swiper.slidePrev()
              }, 500)
            } else {
              swiper.slidePrev();
            }
          } else {
            if(swiper.realIndex === 0){
              this.activeSlide = 0;
              setTimeout(() => {
                swiper.slideNext();
              }, 500)
            } else {
              swiper.slideNext();
            }
          }

          delay = true;
          setTimeout(() => {
            delay = false;
          }, 1550)
        }
      });
    }
  },
  mounted() {
    this.onInit(this.swiper);
  }
}
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>