<template>
  <div :class="{ 'burger-menu_is-open': isOpen }" class="burger-menu">
    <div v-on:click="isOpen = !isOpen" class="burger-menu__btn t-stairs t-stairs__leave-to" data-t-delay="1000">
      <span></span>
      <span></span>
    </div>
    <div class="burger-menu__box">
      <div class="burger-menu__content">
        <!-- Content -->
      </div>
      <div class="burger-menu__background">
        <div class="burger-menu__underlay"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  }
}
</script>

<style scoped lang="scss">
  .burger-menu{
    display: flex;
    justify-content: flex-end;
    &__btn{
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      width: 35px;
      height: 10px;      
      cursor: pointer;
      z-index: 999;
      & span{
        display: block;
        transform: rotate(0);
        transition: .7s;
        width: 100%;
        height: 2px;
        border-bottom: 2px solid #ffffff;
      }
    }
    &__box{
      position: fixed;
      pointer-events: none;
      top: 0;
      right: 0;
      z-index: -1;
      overflow: hidden;
      transition: height 0s,z-index 0s;
      transition-delay: 1s;
    }
    &__content{
      z-index: 1;
      width: 100vw;
      height: 100vh;
    }
    &__underlay{
      width: 100%;
      height: 100%;
      background: darken(#2C2A2A, 5%);
      opacity: .9;
    }
    &__background{
      z-index: -1;
      position: absolute;
      top: 0;
      right: 0;
      width: 300vw;
      height: 300vh;
      transform-origin: right top;
      transform: translateZ(0) rotate(-90deg);
      transition: transform .8s cubic-bezier(.55,.055,.675,.19);
      transition-delay: .2s;
      backdrop-filter: blur(15px);
    }
    &_is-open {
      & .burger-menu__btn span{
        transform: rotate(45deg);
        transition: .7s;
      }
      & .burger-menu__btn span:last-child {
        top: 0;
        transition: .7s;
        transform: rotate(-45deg);
      }
      & .burger-menu__box{
        pointer-events: all;
        z-index: 90;
        transition-delay: 0s;
      }
      & .burger-menu__background {
        transform: translateZ(0) rotate(0deg);
        transition: transform .6s cubic-bezier(.4,0,0,1);
        transition-delay: 0s;
      }
    }
  }
</style>