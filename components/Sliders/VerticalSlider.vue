<template>
  <div class="v-slider" 
      v-swiper:swiper="swiperOption"
      @slideChange="onSlideChange"
    >
    <div class="swiper-wrapper">
      <div class="swiper-slide slide">
        <MainSlider :isActive = "activeSlide === 1"/>
      </div>
      <div class="swiper-slide slide">
        <WorkSlider :isActive = "activeSlide === 2"/>
      </div>
      <div class="swiper-slide slide">
        <div class="c-slide" :class="{ active: activeSlide === 3}">
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
      delay: false,
      touchXDown: 0,
      touchYDown: 0,
      swiperOption: {
        direction: 'vertical',
        allowTouchMove: false,
        spaceBetween: 100,
        speed: 1000,
      }
    }
  },
  mounted() {
    this.onInit();
  },
  methods: {
    onInit: function () {
      const slider = document.querySelector('.v-slider');

      slider.addEventListener("wheel" , this.handleWheel, false);
      slider.addEventListener("touchstart" , this.handleTouchStart, false);
      slider.addEventListener("touchmove" , this.handleTouchMove, false);
    },
    changeSlide: function(to = 'next', delay = 0) {
      if(!this.delay){
        if(delay){
          this.activeSlide = 0;
        }

        // Call activeSlide watcher before actual slide change to wait until slide animation is end
        setTimeout(() => {
          if(to === 'prev'){
            this.swiper.slidePrev()
          } else if(to === 'next'){
            this.swiper.slideNext()
          }
        }, delay)
        
        this.delay = true;
        
        setTimeout(() => {
          this.delay = false;
        }, 1000)
      }
    },
    onSlideChange: function () {
      this.activeSlide = this.swiper.realIndex + 1;
    },
    handleWheel: function (e) {
      if(e.deltaY < 0){
        if(this.swiper.realIndex === 1){
          this.changeSlide('prev', 500);
        } else {
          this.changeSlide('prev');
        }
      } else {
        if(this.swiper.realIndex === 0){
          this.changeSlide('next', 500);
        } else {
          this.changeSlide('next')
        }
      }
    },
    handleTouchStart: function (e) {
      const firstTouch = e.touches[0];
      this.touchXDown = firstTouch.clientX;
      this.touchYDown = firstTouch.clientY;
    },
    handleTouchMove: function (e) {
      let xUp = e.touches[0].clientX;
      let yUp = e.touches[0].clientY;

      let xDiff = this.touchXDown - xUp;
      let yDiff = this.touchYDown - yUp;
      
      if ( Math.abs( xDiff ) <= Math.abs( yDiff ) ) {
        if ( yDiff > 100 && this.swiper.realIndex !== (this.swiper.slides.length - 1)) {
          this.changeSlide('next', 500)
        } else if(yDiff < -100 &&  this.swiper.realIndex !== 0) {
          this.changeSlide('prev', 500)
        }
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
}
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>