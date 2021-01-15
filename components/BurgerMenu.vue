<template>
  <div :class="{ 'burger-menu_is-open': isOpen }" class="burger-menu">
    <div class="burger-menu__btn" v-on:click="isOpen = !isOpen">
      <span></span>
      <span></span>
    </div>
    <div class="burger-menu__box">
      <div class="burger-menu__content container">
        <div class="burger-menu__nav">
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">Разработка</span>
            <ul class="burger-menu-item__links-list">
              <li><a class="burger-menu-item__link" href="#">Корпоративные сайты</a></li>
              <li><a class="burger-menu-item__link" href="#">Промо-магазины</a></li>
              <li><a class="burger-menu-item__link" href="#">Промо-сайты</a></li>
            </ul>
            <div class="burger-menu-divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">Контекстная реклама</span>
            <ul class="burger-menu-item__links-list">
              <li><a class="burger-menu-item__link" href="#">Контекстая реклама Google AdWords</a></li>
              <li><a class="burger-menu-item__link" href="#">Контекстная реклама Яндекс Директ</a></li>
              <li><a class="burger-menu-item__link" href="#">Колл-трекинг сайты</a></li>
            </ul>
            <div class="burger-menu-divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">SEO продвижение</span>
            <ul class="burger-menu-item__links-list">
              <li><a class="burger-menu-item__link" href="#">Продвижение по позициям</a></li>
              <li><a class="burger-menu-item__link" href="#">Продвижение в регионах</a></li>
              <li><a class="burger-menu-item__link" href="#">Продвижение интернет-магазинов</a></li>
            </ul>
            <div class="burger-menu-divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">Аналитика</span>
            <ul class="burger-menu-item__links-list">
              <li><a class="burger-menu-item__link" href="#">Анализ рынка и конкурентов</a></li>
              <li><a class="burger-menu-item__link" href="#">Разработка бренд платформы</a></li>
              <li><a class="burger-menu-item__link" href="#">Аналитика и сегментация</a></li>
            </ul>
            <div class="burger-menu-divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">Сопровождение</span>
            <div class="burger-menu-divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
        </div>
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

<style>
</style>