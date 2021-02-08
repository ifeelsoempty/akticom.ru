<template>
  <div :class="{ 'active': isActive}" class="w-slide">
    <div class="container">
      <div class="w-slide__inner">
        <div class="w-slider__background">
          <div class="w-slider__line" :style="{ backgroundColor: slideData.backgroundColor}">
            <svg width="636" height="1159" viewBox="0 0 636 1159" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path :style="{ fill: slideData.logoColor }" fill-rule="evenodd" clip-rule="evenodd" d="M75.0882 530.616L291.556 19.5364C293.312 13.9686 296.793 9.1197 301.494 5.69303C306.195 2.26635 311.871 0.439942 317.699 0.479133C323.527 0.518325 329.205 2.42117 333.907 5.91108C338.61 9.40099 342.093 14.2965 343.851 19.8879L560.739 533.805C584.338 579.939 553.547 596.055 530.894 585.791C486.675 552.013 420.391 528.881 344.799 523.846C353.282 519.614 360.558 513.306 365.961 505.5C420.014 416.317 349.577 367.905 317.181 284.924C284.911 367.363 214.478 415.026 268.624 504.847C273.883 512.514 280.933 518.775 289.15 523.078L289.924 523.503C214.855 527.589 148.906 549.897 104.834 582.848C82.1239 593.061 51.53 576.46 75.0882 530.616Z" fill="white"/>
              <path :style="{ fill: slideData.logoColor }" fill-rule="evenodd" clip-rule="evenodd" d="M57.8265 710.216C-4.48678 843.487 -14.6943 995.391 22.3522 1009.03C67.2798 1025.43 54.0787 975.005 114.722 996.16C175.365 1017.31 198.887 1151.75 318.169 1158.2C437.518 1153.31 460.825 1019.29 521.515 998.791C582.206 978.295 569.081 1028.58 613.894 1012.64C650.832 999.617 640.494 847.599 578.136 713.512C531.875 614.092 447.655 573.315 344.372 566.917C361.142 579.752 376.834 616.255 371.639 721.991C364.427 869.639 334.866 943.51 317.972 943.174C301.077 942.838 271.477 869.01 264.133 721.289C258.872 615.467 274.467 579.2 291.276 566.557C188.201 571.733 103.972 611.403 57.8265 710.216Z" fill="white"/>
            </svg>
            <div class="w-slide__dark-title">{{ slideData.title }}</div>
          </div>
          <img class="w-slider__rain" :src="slideData.slideRain" alt="">
          <img class="w-slider__pic" :src="slideData.slidePicture" alt="">
        </div>
        <div class="w-slide__info">
          <a :href="slideData.siteLink" target="_blank" class="w-slide__link">{{ slideData.siteName }}</a>
          <div class="w-slide__title">{{ slideData.title }}</div>
          <div class="w-slide__desc">
            {{ slideData.description }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    slideData: Object,
    activeSlide: Number,
    slideIndex: Number,
  },
  data() {
    return {
      isActive: false,
    }
  },
  watch: {
    activeSlide: function(val) {
      if(this.slideIndex + 1 === this.activeSlide){
        this.isActive = true;
      } else {
        this.isActive = false;
      }
    }
  },
  mounted: function () {
  },
  computed: {
  }
}
</script>

<style>

</style>