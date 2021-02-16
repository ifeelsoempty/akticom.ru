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
    onInit: function () {
      const content = document.querySelector('.v-slider');

      content.addEventListener("wheel" , this.handleWheel, false);
      content.addEventListener("touchstart" , this.handleTouchStart, false);
      content.addEventListener("touchmove" , this.handleTouchMove, false);
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
      var xUp = e.touches[0].clientX;
      var yUp = e.touches[0].clientY;

      var xDiff = this.touchXDown - xUp;
      var yDiff = this.touchYDown - yUp;
      
      if ( Math.abs( xDiff ) <= Math.abs( yDiff ) ) {
        if ( yDiff > 0 ) {
          this.changeSlide('next', 500)
        } else {
          this.changeSlide('prev', 500)
        }
      }
    }
  },
  mounted() {
    this.onInit();
  }
}
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>