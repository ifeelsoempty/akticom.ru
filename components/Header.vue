<template>
  <header class="header">
    <div class="container">
      <div class="header-wrapper">
        <div class="header-logo-wrapper">
          <div class="header-logo">
            <img src="@/assets/images/logo-white.png" alt="logo">
          </div>
        </div>
        <div class="header-menu">
          <ul class="header-navbar">
            <li>Проекты</li>
            <li>Услуги</li>
            <li>Команда</li>
          </ul>
          <div class="header-burger">
            <input id="header-burger-toggle" class="header-burger-toggle" type="checkbox" />
            <label class="header-burger-btn" for="header-burger-toggle">
              <span></span>
            </label>
            <div class="header-burger-box">
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {

}
</script>