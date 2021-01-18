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
            <div class="burger-menu-divider burger-menu-item__divider">
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
            <div class="burger-menu-divider burger-menu-item__divider">
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
            <div class="burger-menu-divider burger-menu-item__divider">
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
            <div class="burger-menu-divider burger-menu-item__divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
          <div class="burger-menu-item">
            <span class="burger-menu-item__title">Сопровождение</span>
            <div class="burger-menu-divider burger-menu-item__divider">
              <div class="burger-menu-divider__line"></div>
            </div>
          </div>
        </div>
        <div class="burger-menu__footer">
          <div class="burger-menu__contacts">
            <div class="burger-menu__socials">
              <div class="burger-menu__social-item">
                <img src="@/assets/images/socials/vk.svg" alt="">
              </div>
              <div class="burger-menu__social-item">
                <img src="@/assets/images/socials/inst.svg" alt="">
              </div>
            </div>
            <div class="burger-menu__mail">
              mail@akticom.ru
            </div>
          </div>
          <div class="burger-menu__phones">
            <div class="burger-menu__phone-item">
              +7 (495) 409-32-16
            </div>
            <div class="burger-menu__phone-item">
              +7 (846) 313-23-20
            </div>
          </div>
          <div class="burger-menu__address">
            <div class="burger-menu__city">
              <div :class="{ 'burger-menu__city_selected': address == 'Samara' }" v-on:click="address = 'Samara'" class="burger-menu__city-item">
                Самара
              </div>
              <div class="burger-menu-divider burger-menu__city-divider">
                <div class="burger-menu-divider__line"></div>
              </div>
              <div :class="{ 'burger-menu__city_selected': address == 'Moscow' }" v-on:click="address = 'Moscow'" class="burger-menu__city-item">
                Москва
              </div>
            </div>
            <div class="burger-menu__address-item">
              <span v-if="address == 'Samara'">ул. Ленинская, 168, офис 446</span>
              <span v-if="address == 'Moscow'">ул. Минская, 1 Г, к. 1, офис 9</span>
            </div>
          </div>
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
      isOpen: true,
      address: 'Samara'
    }
  }
}
</script>

<style>
</style>