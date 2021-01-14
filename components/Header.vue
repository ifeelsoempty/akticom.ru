<template>
  <header class="header">
    <div class="container">
      <div class="header-wrapper">
        <div class="header-logo-wrapper">
          <div class="header-logo transition-stairs transition-stairs-leave-to">
            <img src="@/assets/images/logo-white.png" alt="logo">
          </div>
        </div>
        <div class="header-menu">
          <ul class="header-navbar">
            <li class="transition-stairs transition-stairs-leave-to">
              Проекты
            </li>
            <li class="transition-stairs transition-stairs-leave-to">
              Услуги
            </li>
            <li class="transition-stairs transition-stairs-leave-to">
              Команда
            </li>
          </ul>
          <div class="header-burger">
            <input id="header-burger-toggle" class="header-burger-toggle" type="checkbox" />
            <label class="header-burger-btn transition-stairs transition-stairs-leave-to" for="header-burger-toggle">
              <span></span>
            </label>
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
      timeout: 0
    }
  },
  mounted() {
    let arrStairs = Array.from(document.querySelectorAll('.transition-stairs'));
    arrStairs.map(stair => {
      this.timeout += 125;
      setTimeout(() => {
        stair.classList.remove('transition-stairs-leave-to');
      }, this.timeout)
    })
  }
}
</script>

<style lang="scss">
  .transition-stairs {
    transition: transform 1s ease-in-out, opacity 1s ease-in-out, color .3s ease-in-out;
  }
  .transition-stairs-leave-to {
    transform: translateY(-20px);
    opacity: 0;
  }
</style>