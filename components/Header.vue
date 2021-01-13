<template>
  <header class="header">
    <div class="container">
      <div class="header-wrapper">
        <div class="header-logo-wrapper">
          <transition name="slide-fade">
            <div v-if="show" class="header-logo" style="transition-delay: 1s">
              <img src="@/assets/images/logo-white.png" alt="logo">
            </div>
          </transition>
        </div>
        <div class="header-menu">
          <ul class="header-navbar">
            <transition name="slide-fade">
              <li v-if="show" style="transition-delay: .1s">
                Проекты
              </li>
            </transition>
            <transition name="slide-fade">
              <li v-if="show" style="transition-delay: .2s">
                Услуги
              </li>
            </transition>
            <transition name="slide-fade">
              <li v-if="show" style="transition-delay: .3s">
                Команда
              </li>
            </transition>
          </ul>
          <div class="header-burger">
            <input id="header-burger-toggle" class="header-burger-toggle" type="checkbox" />
            <transition name="slide-fade">
              <label v-if="show" class="header-burger-btn" for="header-burger-toggle" style="transition-delay: .4s">
                <span></span>
              </label>
            </transition>
            <div class="header-burger-box">
              <div class="header-burger-box-content">
                <!-- Content -->
              </div>
              <div class="header-burger-box-bg-wrap">
                <div class="header-burger-box-bg"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data(){
    return {
      show: false
    }
  },
  mounted() {
    this.show = true;
  }
}
</script>

<style lang="scss">
  .slide-fade-enter-active {
    transition: all 1s ease-in-out;
  }
  .slide-fade-enter, .slide-fade-leave-to {
    transform: translateY(-20px);
    opacity: 0;
  }
</style>