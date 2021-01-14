<template>
  <header class="header">
    <div class="header__wrapper container">
      <div class="header__logo t-stairs t-stairs__leave-to" data-t-delay="1000">
        <img src="@/assets/images/logo-white.png" alt="akticom-logo">
      </div>
      <nav class="header__nav">
        <ul class="header__links">
          <li class="t-stairs t-stairs__leave-to">
            Проекты
          </li>
          <li class="t-stairs t-stairs__leave-to">
            Услуги
          </li>
          <li class="t-stairs t-stairs__leave-to">
            Команда
          </li>
        </ul>
      </nav>
      <BurgerMenu class="header__burger-menu" />
    </div>
  </header>
</template>

<script>
export default {
  data(){
    return {
      timeout: 250
    }
  },
  mounted() {
    this.stairsTransition();
  },
  methods: {
    stairsTransition: function () {
      const arrStairs = Array.from(document.querySelectorAll('.t-stairs'));

      arrStairs.map(stair => {
        const delay = stair.dataset.tDelay;
        let timeout = this.timeout;
        
        if(delay){
          timeout = delay;
        } else {
          this.timeout += 250;
          console.log(this.timeout);
        }

        setTimeout(() => {
          stair.classList.remove('t-stairs__leave-to');
        }, timeout)
      })
    }
  }
}
</script>

<style lang="scss">
  .header {
    display: flex;
    align-items: center;
    padding: 35px 0;
    color: white;
    position: absolute;
    width: 100vw;
    z-index: 1;
    &__wrapper{
      display: flex;
      align-items: center;
      justify-content: flex-end;
    }
    &__logo{
      width: 150px;
      margin-right: auto;
      & img {
        max-width: 100%;
        height: auto;
      }
    }
    &__nav{
      margin-right: auto
    }
    &__links{
      display: flex;
      list-style: none;
      text-transform: uppercase;
      justify-content: space-between;
      font-size: 14px;
      padding: 0;
      & li {
        font-weight: 300;
        font-size: 15px;
        margin-left: 50px;
        letter-spacing: 0.05rem;
        &:first-child{
          margin-left: 0;
        }
        &:hover{ 
          cursor: pointer;
          color: transparentize(#ffffff, .5)
        }
      }
    }
  }

  .t-stairs {
    transition: transform 1s ease-in-out, opacity 1s ease-in-out, color .3s ease-in-out;
  }
  .t-stairs__leave-to {
    transform: translateY(-20px);
    opacity: 0;
  }

  @media screen and (max-width: 800px){
    .header {
      &__nav{
        display: none;
      }
    }
  }
</style>