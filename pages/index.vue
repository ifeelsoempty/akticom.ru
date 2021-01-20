<template>
  <div class="slider" v-swiper:mySwiper="swiperOption">
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
            <div class="slide__navbar">
              <div class="slide__contact-us">Say Hello</div>
              <ul class="slide__nav">
                <li class="slide__link"><a href="#">Разработка</a></li>
                <li class="slide__link"><a href="#">Сопровождение</a></li>
                <li class="slide__link"><a href="#">Реклама</a></li>
              </ul>
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
            <div class="slide__navbar">
              <div class="slide__contact-us">Say Hello</div>
              <ul class="slide__nav">
                <li class="slide__link"><a href="#">Разработка</a></li>
                <li class="slide__link"><a href="#">Сопровождение</a></li>
                <li class="slide__link"><a href="#">Реклама</a></li>
              </ul>
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
            <div class="slide__navbar">
              <div class="slide__contact-us">Say Hello</div>
              <ul class="slide__nav">
                <li class="slide__link"><a href="#">Разработка</a></li>
                <li class="slide__link"><a href="#">Сопровождение</a></li>
                <li class="slide__link"><a href="#">Реклама</a></li>
              </ul>
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
            <div class="slide__navbar">
              <div class="slide__contact-us">Say Hello</div>
              <ul class="slide__nav">
                <li class="slide__link"><a href="#">Разработка</a></li>
                <li class="slide__link"><a href="#">Сопровождение</a></li>
                <li class="slide__link"><a href="#">Реклама</a></li>
              </ul>
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
          on: {
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