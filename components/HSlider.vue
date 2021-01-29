<template>
  <div class="h-slider" v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__content">
              <div class="slide__subtitle">
                Akticom - это digital-студия
              </div>
              <div class="slide__title">
                Решаем digital задачи
              </div>
              <div class="slide__navbar">
                <div class="slide__contact-us">Say Hello</div>
                <ul class="slide__nav">
                  <li><a class="slide__link" data-swipe-to="1">Разработка</a></li>
                  <li><a class="slide__link" data-swipe-to="2">Сопровождение</a></li>
                  <li><a class="slide__link" data-swipe-to="3">Реклама</a></li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__content">
              <div class="slide__subtitle">
                Проектируем крутые сайты
              </div>
              <div class="slide__title">
                Решаем digital задачи
              </div>
              <div class="slide__navbar">
                <div class="slide__contact-us">Say Hello</div>
                <ul class="slide__nav">
                  <li><a class="slide__link slide__link_active">Разработка</a></li>
                  <li><a class="slide__link" data-swipe-to="2">Сопровождение</a></li>
                  <li><a class="slide__link" data-swipe-to="3">Реклама</a></li>
                </ul>
              </div>
            </div>
            <div class="slide-photo">
              <img class="slide-photo__underlay" src="@/assets/images/slider/slide-photo-1_1.png" alt="">
              <img class="slide-photo__overlay" src="@/assets/images/slider/slide-photo-1_2.png" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__content">
              <div class="slide__subtitle">
                Проектируем крутые сайты
              </div>
              <div class="slide__title">
                Решаем digital задачи
              </div>
              <div class="slide__navbar">
                <div class="slide__contact-us">Say Hello</div>
                <ul class="slide__nav">
                  <li><a class="slide__link" data-swipe-to="1">Разработка</a></li>
                  <li><a class="slide__link slide__link_active">Сопровождение</a></li>
                  <li><a class="slide__link" data-swipe-to="3">Реклама</a></li>
                </ul>
              </div>
            </div>
            <div class="slide-photo">
              <img class="slide-photo__underlay" src="@/assets/images/slider/slide-photo-2_2.png" alt="">
              <img class="slide-photo__overlay" src="@/assets/images/slider/slide-photo-2_1.png" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slide__content">
              <div class="slide__subtitle">
                Проектируем крутые сайты
              </div>
              <div class="slide__title">
                Решаем digital задачи
              </div>
              <div class="slide__navbar">
                <div class="slide__contact-us">Say Hello</div>
                <ul class="slide__nav">
                  <li><a class="slide__link" data-swipe-to="1">Разработка</a></li>
                  <li><a class="slide__link" data-swipe-to="2">Сопровождение</a></li>
                  <li><a class="slide__link slide__link_active">Реклама</a></li>
                </ul>
              </div>
            </div>
            <div class="slide-photo">
              <img class="slide-photo__underlay" src="@/assets/images/slider/slide-photo-3_1.png" alt="">
              <img class="slide-photo__overlay" src="@/assets/images/slider/slide-photo-3_2.png" alt="">
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="slider-btn-next">
      <div class="slider-btn-next__title">Next</div>
      <div class="slider-btn-next__background"></div> 
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
      theme: 'blue',
      swiperOption: {
        on: {
          init(swiper) {
            const links = Array.from(document.querySelectorAll('.slide__link'));
            links.map(link => {
              link.addEventListener('click', () => {
                let slideIndex = link.dataset.swipeTo;
                if(slideIndex){
                  swiper.slideTo(link.dataset.swipeTo);
                } 
              })
            })

            const nextBtn = document.querySelector('.slider-btn-next');
            nextBtn.addEventListener('click', () => {
              if(swiper.realIndex == (swiper.slides.length - 1)){
                swiper.slideTo(0);
              }else{
                swiper.slideNext();
              }
            })
          },
          progress (swiper) {
            const dataThemeVal = swiper.$el[0].dataset.theme;
            const progress = swiper.progress;
            const slideStep = 1 / (swiper.slides.length - 1);
            const halfSlideStep = slideStep / 2;

            changeSlideOnProgress(1, 'beige-theme');
            changeSlideOnProgress(2, 'blue-theme');
            changeSlideOnProgress(3, 'purple-theme');

            function changeSlideOnProgress(slideIndex, themeClass){
              if(progress > halfSlideStep){
                if((progress > (halfSlideStep) + (slideStep * (slideIndex - 1))) && (progress <= (slideStep * slideIndex) + halfSlideStep)){
                  if(dataThemeVal !== themeClass){
                    swiper.$el[0].dataset.theme = themeClass;
                    document.body.classList.add(themeClass);
                    swiper.slides[slideIndex].classList.add('slide_progress-active');
                  }
                } else {
                  if(dataThemeVal == themeClass){
                    document.body.classList.remove(themeClass);
                    swiper.slides[slideIndex].classList.remove('slide_progress-active');
                  }
                }
              } else {
                  document.body.classList.remove(themeClass);
                  swiper.$el[0].dataset.theme = 'default-theme';
              }
            }
          },
        }
      }
    }
  },
}
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>