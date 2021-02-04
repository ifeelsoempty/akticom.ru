<template>
  <div class="w-slider" :class="{ 'active': isActive }">
    <div class="w-slider__static container">
      <div class="w-progress">
        <div class="w-progress__number"></div>
        <div class="w-progress__line">
          <div class="w-progress__underline"></div>
        </div>
      </div>
    </div>
    <div class="w-slides">
      <div :class="{ active: activeSlide === 1 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_blue">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">HORIBA</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-1.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-1.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="http://horiba.ru/" target="_blank" class="w-slide__link">horiba.ru</a>
              <div class="w-slide__title">HORIBA</div>
              <div class="w-slide__desc">
                Является российской компанией, входящей в состав HORIBA Group со штаб-квартирой в г. Киото, Япония. 
                Вместе с разработкой приборов и систем в рамках сотрудничества HORIBA Group
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 2 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_yellow">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">AgentStudios</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-2.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-2.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="https://agentstudios.ru/" target="_blank" class="w-slide__link">agentstudios.ru</a>
              <div class="w-slide__title">AgentStudios</div>
              <div class="w-slide__desc">
                Поиск студий и локаций для съемок
                Мы придумали абсолютно новый сервис по бронированию студий и локаций для фото- и видеосъемки!
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 3 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_purple">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">TaxiBooster</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-3.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-3.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="https://booster.taxi/" target="_blank" class="w-slide__link">booster.taxi</a>
              <div class="w-slide__title">TaxiBooster</div>
              <div class="w-slide__desc">
                Это полный набор инструментов, которые раскроют 
                потенциал вашего таксопарка и повысят его эффективность
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 4 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_red">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">Сувенировед</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-4.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-4.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="https://www.suveniroved.ru/" target="_blank" class="w-slide__link">suveniroved.ru</a>
              <div class="w-slide__title">Сувенировед</div>
              <div class="w-slide__desc">
                Решает любые комплексные задачи по дизайну на сувенирную продукцию 
                – от простого макетирования до создания индивидуальных сложных проектов.
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 5 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_dark-yellow">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">Металлмос<br>комплект</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-5.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-5.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="https://metmos.com/" target="_blank" class="w-slide__link">metmos.com</a>
              <div class="w-slide__title">Металлмос<br>комплект</div>
              <div class="w-slide__desc">
                Реализует 35000 позиций металлопроката по территории Российской Федерации, в странах СНГ и ближнего зарубежья. 
                Стремимся развивать долгосрочные партнерские отношения с нашими клиентами.
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 6 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_dark-blue">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">Металл<br>гарант</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-6.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-6.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="https://m-garant.tk/" target="_blank" class="w-slide__link">m-garant.tk</a>
              <div class="w-slide__title">Металл<br>гарант</div>
              <div class="w-slide__desc">
                Миссия компании - снабжать строительные, промышленные, муниципальные и металлообрабатывающие предприятия 
                продукцией российских металлопрокатных заводов, а так же металлоконструкциями своего завода 
                — в требуемом объеме, в точные сроки, в нужном виде.
              </div>
            </div>
          </div>
        </div>
      </div>
      <div :class="{ active: activeSlide === 7 }" class="w-slide">
        <div class="container">
          <div class="w-slide__inner">
            <div class="w-slider__background">
              <div class="w-slider__line w-slider__line_gray">
                <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
                </svg>
                <div class="w-slide__dark-title">Lass Print</div>
              </div>
              <img class="w-slider__rain" src="@/assets/images/works/rains/slide-7.png" alt="">
              <img class="w-slider__pic" src="@/assets/images/works/slide-pics/slide-7.png" alt="">
            </div>
            <div class="w-slide__info">
              <a href="http://lass-print.akticom-test.ru/" target="_blank" class="w-slide__link">lass-print.akticom-test.ru</a>
              <div class="w-slide__title">Lass Print</div>
              <div class="w-slide__desc">
                Компания развивается на рынке с 2009 года. За этот срок из маленькой 
                организации мы выросли в Гипермаркет расходных материалов с тысячами наименований продукции.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    isActive: Boolean,
  },
  data() {
    return {
      activeSlide: 0,
      slideAmount: 7,
      transitionDelay: 500,
      delay: false,
      timeoutID: '',
    }
  },
  watch: {
    isActive: function(isActive) {
      if(isActive){
        this.activeSlide = 1;
        this.delay = true;
      } else {
        this.activeSlide = 0;
        this.delay = false;
      }
    },
    activeSlide: function(activeSlide) {
      this.updateProgress(activeSlide);
    },
    delay: function(delay) {
      clearTimeout(this.timeoutID);
      if(delay){
        this.timeoutID = setTimeout(() => {
          this.delay = false;
        }, this.transitionDelay * 2)
      }
    },
  },
  mounted() {
    const wSlider = document.querySelector('.w-slider');

    wSlider.addEventListener("wheel" , (e) => this.onWheel(e))
  },
  methods: {
    onWheel: function (e) {
      if(this.isActive){
        // Stop v-slider wheel propagation
        if(this.delay || this.activeSlide !== 1 || e.deltaY > 0){
          e.stopPropagation()
        }
  
        // Change slide with delay
        if(!this.delay){
          if(e.deltaY < 0){
            if(this.activeSlide > 1){
              this.activeSlide = this.activeSlide - 1;
            }
          } else {
            if(this.activeSlide < this.slideAmount){
              this.activeSlide = this.activeSlide + 1;
            }
          }
          this.delay = true;
        }
      }
    },
    updateProgress: function (slideNumber) {
      let progressUnderline = document.querySelector('.w-progress__underline');
      let progressNumber = document.querySelector('.w-progress__number');
      let progressPercent = ((100 / this.slideAmount) * slideNumber);

      progressUnderline.style.height =`${progressPercent}%`;
      progressNumber.style.top = `${progressPercent - 9}%`;
      progressNumber.innerHTML = ('0' + slideNumber).slice(-2);
    }
  }
}
</script>
