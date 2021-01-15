<template>
  <div :class="{ 'burger-menu_is-open': isOpen }" class="burger-menu">
    <div v-on:click="isOpen = !isOpen" class="burger-menu__btn t-stairs t-stairs__leave-to" data-t-delay="1000">
      <span></span>
      <span></span>
    </div>
    <div class="burger-menu__box">
      <div class="burger-menu__content container">
        <transition name="burger-menu">
          <div v-if="isOpen" class="burger-menu__nav">
            <div class="burger-menu-item">
              <div class="burger-menu-item__title">Разработка</div>
              <ul class="burger-menu-item__links-list">
                <li><a class="burger-menu-item__link" href="#">Корпоративные сайты</a></li>
                <li><a class="burger-menu-item__link" href="#">Промо-магазины</a></li>
                <li><a class="burger-menu-item__link" href="#">Промо-сайты</a></li>
              </ul>
              <div class="burger-menu-item__divider"></div>
            </div>
            <div class="burger-menu-item">
              <div class="burger-menu-item__title">
                <span>Контекстная реклама</span>
              </div>
              <ul class="burger-menu-item__links-list">
                <li><a class="burger-menu-item__link" href="#">Контекстая реклама Google AdWords</a></li>
                <li><a class="burger-menu-item__link" href="#">Контекстная реклама Яндекс Директ</a></li>
                <li><a class="burger-menu-item__link" href="#">Колл-трекинг сайты</a></li>
              </ul>
              <div class="burger-menu-item__divider"></div>
            </div>
            <div class="burger-menu-item">
              <div class="burger-menu-item__title">
                <span>SEO продвижение</span>
              </div>
              <ul class="burger-menu-item__links-list">
                <li><a class="burger-menu-item__link" href="#">Продвижение по позициям</a></li>
                <li><a class="burger-menu-item__link" href="#">Продвижение в регионах</a></li>
                <li><a class="burger-menu-item__link" href="#">Продвижение интернет-магазинов</a></li>
              </ul>
              <div class="burger-menu-item__divider"></div>
            </div>
            <div class="burger-menu-item">
              <div class="burger-menu-item__title">
                <span>Аналитика</span>
              </div>
              <ul class="burger-menu-item__links-list">
                <li><a class="burger-menu-item__link" href="#">Анализ рынка и конкурентов</a></li>
                <li><a class="burger-menu-item__link" href="#">Разработка бренд платформы</a></li>
                <li><a class="burger-menu-item__link" href="#">Аналитика и сегментация</a></li>
              </ul>
            </div>
            <div class="burger-menu-item">
              <div class="burger-menu-item__title">
                <span>Сопровождение</span>
              </div>
              <div class="burger-menu-item__divider"></div>
            </div>
          </div>
        </transition>
        <div class="burger-menu__footer">

        </div>
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
      width: 100vw;
      height: 100vh;
      overflow: hidden;
      transition: height 0s,z-index 0s;
      transition-delay: 1s;
    }
    &__content{
      padding: 120px 0;
      height: 100%;
    }
    &__nav{
      display: flex;
      flex-wrap: wrap;
    }
    &-item{
      display: flex;
      align-items: center;
      margin-bottom: 25px;
      &__title{
        display: inline-block;
        width: min-content;
        font-size: 47px;
        font-weight: 800;
      }
      &__links-list{
        list-style: none;
        padding: 0;
        margin-left: 50px;
        & li {
          margin-top: 10px;
          &:first-child{
            margin-top: 0;
          }
        }
      }
      &__link{
        color: #ffffff;
        font-size: 14px;
        font-weight: 200;
        text-decoration: none;
      }
      &__divider{
        width: 1px;
        height: 100px;
        margin: 0 40px;
        background: #ffffff;
        transform: rotate(25deg);
      }
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
      transform: rotate(-90deg);
      transition: transform .5s cubic-bezier(.55,.055,.675,.19);
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
        transition-delay: 0s;
      }
    }
  }

  .burger-menu-enter-active,
  .burger-menu-leave-active {
    transition-duration: .5s;
  }

  .burger-menu-enter-active {
    transition-delay: .5s;
  }
  .burger-menu-leave-active {
    transition-delay: 0s;
  }
  .burger-menu-enter, .burger-menu-leave-to {
    opacity: 0;
    transform:  translate(100px, 100px);
  }
</style>