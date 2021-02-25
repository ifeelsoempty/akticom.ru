<template>
  <div class="h-slider" :class="{ 'active': isActive }">
    <div class="h-slider__swiper" v-swiper:mySwiper="swiperOption">
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
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="1">Разработка</a></li>
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="2">Сопровождение</a></li>
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="3">Реклама</a></li>
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
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="2">Сопровождение</a></li>
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="3">Реклама</a></li>
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
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="1">Разработка</a></li>
                    <li><a class="slide__link slide__link_active">Сопровождение</a></li>
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="3">Реклама</a></li>
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
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="1">Разработка</a></li>
                    <li><a class="slide__link" data-cursor-type="medium" data-swipe-to="2">Сопровождение</a></li>
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
      <div class="slider-btn-next" data-cursor-type="large">
        <div class="slider-btn-next__content">
          <div class="slider-btn-next__title">Next</div>
          <svg class="slider-btn-next__arrow" width="60" height="13" viewBox="0 0 93 13" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M0.5 6.5H91.5M91.5 6.5L86.3705 1M91.5 6.5L86.3705 12" stroke="white"/>
          </svg>
        </div>
        <div class="slider-btn-next__background"></div> 
      </div>
      <div class="slider-static container">
        <div class="cursor-magnet">
          <div class="slider-scroll">
            <svg class="slider-scroll__finger" width="30" height="35" viewBox="0 0 30 35" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M27.2126 13.7917H27.1642C26.5219 13.7865 25.8992 14.019 25.411 14.4464C24.9971 13.346 23.996 12.5586 22.8267 12.5586C22.1165 12.566 21.4375 12.8588 20.9363 13.3744C20.4719 12.428 19.5288 11.828 18.4943 11.8207H18.4432C17.8704 11.8207 17.3103 11.9725 16.9252 12.2943V5.62022C16.9252 3.96239 15.6618 2.61377 14.127 2.61377C12.5938 2.61377 11.3381 3.96116 11.3369 5.61806L11.324 18.9093L10.658 18.0815C10.0004 17.2435 9.03237 16.723 7.98522 16.6444C6.95973 16.5727 5.95079 16.9379 5.19754 17.6537L4.55348 18.2006C4.33028 18.39 4.2662 18.7137 4.40037 18.977L10.6721 31.3169C11.8264 33.587 14.0229 35 16.4048 35H23.4395C27.049 35 29.9889 31.7968 29.9925 27.863C29.994 26.1156 29.9958 24.8125 29.997 23.7565C30.0006 20.9281 30.0021 19.8877 29.9949 16.7719C29.991 15.1187 28.7429 13.7917 27.2126 13.7917ZM28.7648 23.7534C28.7636 24.8098 28.7618 26.1143 28.7603 27.8618C28.7573 31.1007 26.3703 33.7385 23.4395 33.7385H16.4048C14.4841 33.7385 12.7066 32.5858 11.7653 30.7346L5.72246 18.8477L5.99501 18.6155C6.00283 18.6087 6.01095 18.6013 6.01847 18.5942C6.52445 18.1067 7.2052 17.8563 7.89828 17.9031C8.60671 17.9589 9.26069 18.3134 9.70379 18.8822L11.4591 21.0697C11.6242 21.2755 11.8977 21.3528 12.1425 21.2631C12.3874 21.1735 12.551 20.9358 12.551 20.6697L12.5616 5.61868C12.5622 4.65749 13.273 3.87524 14.1276 3.87524C14.9822 3.87524 15.6931 4.6578 15.6931 5.62022V14.6947C15.6931 14.7264 15.6916 14.7584 15.6916 14.7904C15.6916 14.8046 15.6931 14.8191 15.6931 14.8333V18.7113C15.6931 19.0596 15.9689 19.342 16.3092 19.342C16.6494 19.342 16.9252 19.0596 16.9252 18.7113V14.7159C16.9252 13.7886 17.6105 13.0821 18.4432 13.0821H18.4943C19.3492 13.0821 20.0826 13.8286 20.0826 14.7911V18.3414C20.0826 18.6897 20.3585 18.9721 20.6987 18.9721C21.0389 18.9721 21.3148 18.6897 21.3148 18.3414V15.5558C21.3148 14.5937 21.9976 13.8108 22.8574 13.8108C23.7123 13.8108 24.3952 14.5933 24.3952 15.5558V18.1837C24.3952 18.532 24.671 18.8144 25.0112 18.8144C25.3515 18.8144 25.6273 18.532 25.6273 18.1837V16.7606C25.6273 15.7988 26.3096 15.0531 27.1642 15.0531H27.2126C28.0651 15.0531 28.7603 15.8148 28.7627 16.7741C28.77 19.8877 28.7684 20.9268 28.7648 23.7534Z" fill="#939393"/>
              <path d="M5.38735 14.8323C5.1467 14.5859 4.75654 14.5859 4.51618 14.8323L3.44858 15.9253V2.80564L4.51618 3.89833C4.75684 4.14471 5.147 4.14471 5.38735 3.89833C5.62801 3.65195 5.62801 3.25251 5.38735 3.00613L3.42211 0.994448C3.35593 0.769935 3.17333 0.601473 2.94802 0.557433C2.72301 0.513393 2.49258 0.601165 2.35029 0.785333L2.34819 0.787181L0.180491 3.00613C-0.0601636 3.25251 -0.0601636 3.65195 0.180491 3.89833C0.420845 4.14471 0.811006 4.14471 1.05166 3.89833L2.21643 2.70586V16.0251L1.05166 14.8323C0.811006 14.5859 0.421145 14.5859 0.180491 14.8323C-0.0601636 15.0787 -0.0601636 15.4781 0.180491 15.7242L2.34819 17.9438C2.58884 18.1902 2.979 18.1902 3.21966 17.9438L5.38735 15.7242C5.62801 15.4781 5.62801 15.0787 5.38735 14.8323Z" fill="#939393"/>
              <path d="M10.1731 5.28637C10.1731 3.06342 11.9332 1.26146 14.1045 1.26146C16.2758 1.26146 18.0359 3.06342 18.0359 5.28637C18.0359 5.63469 18.3117 5.9171 18.6519 5.9171C18.9922 5.9171 19.268 5.63469 19.268 5.28637C19.268 2.36678 16.9562 0 14.1045 0C11.2527 0 8.94092 2.36678 8.94092 5.28637C8.94092 5.63469 9.21677 5.9171 9.55699 5.9171C9.89722 5.9171 10.1731 5.63469 10.1731 5.28637Z" fill="#939393"/>
            </svg>
            <svg class="slider-scroll__mouse" width="34px" height="50px" viewBox="0 0 247 390" fill="none" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
              <path class="slider-scroll__wheel" d="M123.359,79.775l0,72.843" stroke="#F2EFE8" stroke-width="15"/>
              <path d="M236.717,123.359c0,-62.565 -50.794,-113.359 -113.358,-113.359c-62.565,0 -113.359,50.794 -113.359,113.359l0,143.237c0,62.565 50.794,113.359 113.359,113.359c62.564,0 113.358,-50.794 113.358,-113.359l0,-143.237Z" stroke="#F2EFE8" stroke-width="15"/>
            </svg>
          </div>
          <div class="cursor-magnet__trigger"></div>
        </div>
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
  props: {
    isActive: Boolean,
  },
  data() {
    return {
      theme: 'blue',
      swiperOption: {
        speed: 1000,
        roundLengths: true,
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
            changeSlideOnProgress(2, 'yellow-theme');
            changeSlideOnProgress(3, 'red-theme');

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