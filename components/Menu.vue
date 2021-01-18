<template>
  <div :class="{ 'menu_is-open': isOpen }" class="menu">
    <div class="menu__btn" v-on:click="isOpen = !isOpen">
      <span></span>
      <span></span>
    </div>
    <div class="menu__box">
      <div class="menu__content container">
        <div class="menu-nav">
          <div class="menu-item">
            <span class="menu-item__title">Разработка</span>
            <ul class="menu-item__links-list">
              <li><a class="menu-item__link" href="#">Корпоративные сайты</a></li>
              <li><a class="menu-item__link" href="#">Промо-магазины</a></li>
              <li><a class="menu-item__link" href="#">Промо-сайты</a></li>
            </ul>
            <div class="menu-divider menu-item__divider">
              <div class="menu-divider__line"></div>
            </div>
          </div>
          <div class="menu-item">
            <span class="menu-item__title">Контекстная реклама</span>
            <ul class="menu-item__links-list">
              <li><a class="menu-item__link" href="#">Контекстая реклама Google AdWords</a></li>
              <li><a class="menu-item__link" href="#">Контекстная реклама Яндекс Директ</a></li>
              <li><a class="menu-item__link" href="#">Колл-трекинг сайты</a></li>
            </ul>
            <div class="menu-divider menu-item__divider">
              <div class="menu-divider__line"></div>
            </div>
          </div>
          <div class="menu-item">
            <span class="menu-item__title">SEO продвижение</span>
            <ul class="menu-item__links-list">
              <li><a class="menu-item__link" href="#">Продвижение по позициям</a></li>
              <li><a class="menu-item__link" href="#">Продвижение в регионах</a></li>
              <li><a class="menu-item__link" href="#">Продвижение интернет-магазинов</a></li>
            </ul>
            <div class="menu-divider menu-item__divider">
              <div class="menu-divider__line"></div>
            </div>
          </div>
          <div class="menu-item">
            <span class="menu-item__title">Аналитика</span>
            <ul class="menu-item__links-list">
              <li><a class="menu-item__link" href="#">Анализ рынка и конкурентов</a></li>
              <li><a class="menu-item__link" href="#">Разработка бренд платформы</a></li>
              <li><a class="menu-item__link" href="#">Аналитика и сегментация</a></li>
            </ul>
            <div class="menu-divider menu-item__divider">
              <div class="menu-divider__line"></div>
            </div>
          </div>
          <div class="menu-item">
            <span class="menu-item__title">Сопровождение</span>
            <div class="menu-divider menu-item__divider">
              <div class="menu-divider__line"></div>
            </div>
          </div>
        </div>
        <div class="menu-footer">
          <div class="menu__contacts menu-footer__col">
            <div class="menu__socials menu-footer__row">
              <div class="menu__social-item">
                <img src="@/assets/images/socials/vk.svg" alt="">
              </div>
              <div class="menu__social-item">
                <img src="@/assets/images/socials/inst.svg" alt="">
              </div>
            </div>
            <div class="menu__mail menu-footer__row">
              mail@akticom.ru
            </div>
          </div>
          <div class="menu__phones menu-footer__col">
            <div class="menu__phone-item menu-footer__row">
              +7 (495) 409-32-16
            </div>
            <div class="menu__phone-item menu-footer__row">
              +7 (846) 313-23-20
            </div>
          </div>
          <div class="menu__address menu-footer__col">
            <div class="menu__city menu-footer__row">
              <div :class="{ 'menu__city_selected': address == 'Samara' }" v-on:click="address = 'Samara'" class="menu__city-item">
                Самара
              </div>
              <div class="menu-divider menu__city-divider">
                <div class="menu-divider__line"></div>
              </div>
              <div :class="{ 'menu__city_selected': address == 'Moscow' }" v-on:click="address = 'Moscow'" class="menu__city-item">
                Москва
              </div>
            </div>
            <div class="menu__address-item menu-footer__row">
              <span v-if="address == 'Samara'">ул. Ленинская, 168, офис 446</span>
              <span v-if="address == 'Moscow'">ул. Минская, 1 Г, к. 1, офис 9</span>
            </div>
          </div>
        </div>
      </div>
      <div class="menu__background">
        <div class="menu__underlay"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      address: 'Samara'
    }
  }
}
</script>

<style>
</style>