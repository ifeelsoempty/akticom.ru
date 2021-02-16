<template>
  <div class="v-slider" 
      v-swiper:swiper="swiperOption"
      @slideChange="onSlideChange"
    >
    <div class="swiper-wrapper">
      <div class="swiper-slide slide">
        <MainSlider :isActive = "activeSlide === 1 ? true : false"/>
      </div>
      <div class="swiper-slide slide">
        <WorkSlider :isActive = "activeSlide === 2 ? true : false"/>
      </div>
      <div class="swiper-slide slide">
        <div class="c-slide" :class="{ active: activeSlide === 3 ? true : false }">
          <div class="c-slide__container container">
            <div class="c-slide__inner">
              <div class="c-slide__content">
                <div class="c-slide__subtitle">Есть интересная задача?</div>
                <div data-cursor-type="large" class="c-slide__title">Давайте обсудим</div>
                <img class="c-slide__arrow" src="@/assets/images/arrow.svg" alt="">
              </div>
              <Footer class="c-slide__footer" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { directive } from 'vue-awesome-swiper'

import 'swiper/swiper-bundle.css'

import MainSlider from './MainSlider'
import WorkSlider from './WorkSlider'
import Footer from '../Footer'


export default {
  directives: {
    swiper: directive
  },
  components: {
    MainSlider, WorkSlider, Footer
  },
  data() {
    return {
      activeSlide: 1,
      swiperOption: {
        direction: 'vertical',
        allowTouchMove: false,
        spaceBetween: 100,
        speed: 1000,
      }
    }
  },
  watch: {
    activeSlide: function (activeSlide){
      const mainSlider = document.querySelector('.h-slider__swiper');

      if(activeSlide === 1){
        document.body.classList.add(mainSlider.dataset.theme)
      } else {
        document.body.classList.remove(mainSlider.dataset.theme);
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
          }, 1000)
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