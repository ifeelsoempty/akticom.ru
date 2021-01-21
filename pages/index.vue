<template>
  <div class="slider" v-swiper:mySwiper="swiperOption">
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
          </div>
        </div>
      </div>
      <div class="swiper-slide slide">
        <div class="slide-container container">
          <div class="slide__inner">
            <div class="slider__content">
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
          </div>
        </div>
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
    <div class="slider-btn-next">
      <div class="slider-btn-next__title">Next</div>
      <div class="slider-btn-next__background"></div> 
    </div>
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
          on: {
            init(swiper) {
              const content = document.querySelector('.swiper-container');

              let delay = false;
              content.addEventListener("wheel" , (e) => {
                if(!delay){
                  e.deltaY < 0 ? swiper.slidePrev() : swiper.slideNext();
                  delay = true;
                  setTimeout(() => {
                    delay = false;
                  }, 500)
                }
              });

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
              changeThemeOnProgress(swiper, 1, 'beige-theme');
              changeThemeOnProgress(swiper, 2, 'blue-theme');
              changeThemeOnProgress(swiper, 3, 'purple-theme');

              function changeThemeOnProgress(swiper, slideIndex, themeClass){
                let progress = swiper.progress;
                let slideStep = 1 / (swiper.slides.length - 1);
                let halfSlideStep = slideStep / 2;

                if(slideIndex == 0){
                  console.log(progress);
                  if(progress <= halfSlideStep){
                    document.body.classList.add(themeClass)
                  } else {
                    document.body.classList.remove(themeClass)
                  }
                } else {
                  if((progress > (halfSlideStep) + (slideStep * (slideIndex - 1))) && (progress <= (slideStep * slideIndex) + halfSlideStep)){
                    document.body.classList.add(themeClass)
                  } else {
                    document.body.classList.remove(themeClass)
                  }
                }
              }
            },
          }
        }
      }
    },
    mounted() {
    }
  }
</script>

<style>
.swiper-container{
  width: 100vw;
  height: 100vh;
}
</style>