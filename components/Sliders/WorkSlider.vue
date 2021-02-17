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
      <WorkSlide 
        v-for="(slide, index) in slides" 
        :key="index" 
        :slideData="slide"
        :isActive="(activeSlide === (index + 1)) && isActive"
      />
    </div>
  </div>
</template>

<script>
import WorkSlide from './Slides/WorkSlide'

export default {
  components: {
    WorkSlide
  },
  props: {
    isActive: Boolean,
  },
  data() {
    return {
      slides: [
        {
          title: 'HORIBA',
          siteName: 'horiba.ru',
          siteLink: 'http://horiba.ru/',
          description: 'Является российской компанией, входящей в состав HORIBA Group со штаб-квартирой в г. Киото, Япония. Вместе с разработкой приборов и систем в рамках сотрудничества HORIBA Group',
          slideRain: require('@/assets/images/works/rains/slide-1.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-1.png'),
          backgroundColor: '#4784C3',
          logoColor: '#528ECC',
        },
        {
          title: 'AgentStudios',
          siteName: 'agentstudios.ru',
          siteLink: 'https://agentstudios.ru/',
          description: 'Поиск студий и локаций для съемок. Мы придумали абсолютно новый сервис по бронированию студий и локаций для фото- и видеосъемки!',
          slideRain: require('@/assets/images/works/rains/slide-2.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-2.png'),
          backgroundColor: '#FFD542',
          logoColor: '#F4CC3E',
        },
        {
          title: 'TaxiBooster',
          siteName: 'booster.taxi',
          siteLink: 'https://booster.taxi/',
          description: 'Это полный набор инструментов, которые раскроют потенциал вашего таксопарка и повысят его эффективность',
          slideRain: require('@/assets/images/works/rains/slide-3.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-3.png'),
          backgroundColor: '#8B326B',
          logoColor: '#843066',
        },
        {
          title: 'Сувенировед',
          siteName: 'horiba.ru',
          siteLink: 'https://www.suveniroved.ru/',
          description: 'Решает любые комплексные задачи по дизайну на сувенирную продукцию – от простого макетирования до создания индивидуальных сложных проектов.',
          slideRain: require('@/assets/images/works/rains/slide-4.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-4.png'),
          backgroundColor: '#DB0703',
          logoColor: '#CC100D',
        },
        {
          title: 'Металлмос комплект',
          siteName: 'metmos.com',
          siteLink: 'https://metmos.com/',
          description: 'Реализует 35000 позиций металлопроката по территории Российской Федерации, в странах СНГ и ближнего зарубежья. Стремимся развивать долгосрочные партнерские отношения с нашими клиентами.',
          slideRain: require('@/assets/images/works/rains/slide-5.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-5.png'),
          backgroundColor: '#FBB91B',
          logoColor: '#FAB40C',
        },
        {
          title: 'Металл гарант',
          siteName: 'm-garant.tk',
          siteLink: 'https://m-garant.tk/',
          description: 'Миссия компании - снабжать строительные, промышленные, муниципальные и металлообрабатывающие предприятия продукцией российских металлопрокатных заводов, а так же металлоконструкциями своего завода — в требуемом объеме, в точные сроки, в нужном виде.',
          slideRain: require('@/assets/images/works/rains/slide-6.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-6.png'),
          backgroundColor: '#063F7D',
          logoColor: '#084384',
        },
        {
          title: 'Lass Print',
          siteName: 'lass-print.akticom-test.ru',
          siteLink: 'http://lass-print.akticom-test.ru/',
          description: 'Компания развивается на рынке с 2009 года. За этот срок из маленькой организации мы выросли в Гипермаркет расходных материалов с тысячами наименований продукции.',
          slideRain: require('@/assets/images/works/rains/slide-7.png'),
          slidePicture: require('@/assets/images/works/slide-pics/slide-7.png'),
          backgroundColor: '#3B3B3B',
          logoColor: '#3F3F3F',
        },
      ],
      activeSlide: 1,
      transitionDuration: 500,
      delay: false,
      timeoutID: '',
    }
  },
  mounted() {
    this.onInit();
  },
  methods: {
    onInit: function () {
      const slider = document.querySelector('.w-slider');

      slider.addEventListener("wheel" , this.handleWheel, false)
      slider.addEventListener("touchstart" , this.handleTouchStart, false);
      slider.addEventListener("touchmove" , this.handleTouchMove, false);
    },
    changeSlide: function (to) {
      if(!this.delay){
        if(to === 'next'){
          if(this.activeSlide < this.slidesAmount){
            this.activeSlide = this.activeSlide + 1;
          }
        } else if (to === 'prev'){
          if(this.activeSlide > 1){
            this.activeSlide = this.activeSlide - 1;
          }
        }
        this.delay = true;
      }
    },
    handleWheel: function (e) {
      if(this.isActive){
        // Stop v-slider wheel propagation
        if(this.delay || !((this.activeSlide === 1 && e.deltaY < 0) || (this.activeSlide === this.slidesAmount && e.deltaY > 0))){
          e.stopPropagation()
        }
        // Change slide with delay
        if(e.deltaY > 0){
          this.changeSlide('next')
        } else {
          this.changeSlide('prev')
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

      if(this.delay || !((this.activeSlide === 1 && yDiff < 0) || (this.activeSlide === this.slidesAmount && yDiff > 0))){
        e.stopPropagation()
      }
      
      if ( Math.abs( xDiff ) <= Math.abs( yDiff ) ) {
        if ( yDiff > 100 ) {
          this.changeSlide('next')
        } else if(yDiff < -100) {
          this.changeSlide('prev')
        }
      }
    },
    updateProgress: function (slideNumber) {
      let progressUnderline = document.querySelector('.w-progress__underline');
      let progressNumber = document.querySelector('.w-progress__number');
      let progressPercent = ((100 / this.slidesAmount) * slideNumber);

      progressUnderline.style.height =`${progressPercent}%`;
      progressNumber.style.top = `${progressPercent - 9}%`;
      progressNumber.innerHTML = ('0' + slideNumber).slice(-2);
    },
  },
  watch: {
    isActive: function(isActive) {
      this.delay = true;
      if(isActive) this.updateProgress(this.activeSlide);
    },
    activeSlide: function(activeSlide) {
      this.updateProgress(activeSlide);
    },
    delay: function(delay) {
      clearTimeout(this.timeoutID);
      if(delay){
        this.timeoutID = setTimeout(() => {
          this.delay = false;
        }, this.transitionDuration * 2)
      }
    },
  },
  computed: {
    slidesAmount() {
      return this.slides.length;
    }
  },
}
</script>
