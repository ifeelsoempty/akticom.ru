<template>
  <header class="header">
    <div class="header__wrapper container">
      <svg class="header__logo t-stairs t-stairs__leave-to" data-t-delay="500" width="50" height="67" viewBox="0 0 50 67" xmlns="http://www.w3.org/2000/svg">
        <path fill="white" d="M18.5124 21.9928L46.9022 0.463598C47.1779 0.209847 47.5268 0.0511071 47.8982 0.0104008C48.2697 -0.0303055 48.6443 0.0491279 48.9678 0.237204C49.2914 0.425279 49.5469 0.712221 49.6975 1.05637C49.848 1.40051 49.8857 1.78397 49.8051 2.15113L45.4729 37.6602C45.3141 40.9795 43.0834 40.894 42.149 39.6004C40.7641 36.3109 37.8095 32.9098 33.758 30.2186C34.3659 30.2537 34.9729 30.1349 35.5234 29.8729C41.3845 26.6354 39.0061 21.6954 39.8519 16.0455C35.42 19.6027 29.9725 20.0079 30.1202 26.732C30.1684 27.3263 30.3611 27.8995 30.6816 28.401L30.7111 28.4493C26.3974 26.2822 22.0099 25.4199 18.5013 25.8473C16.9095 25.6912 15.7351 23.7918 18.5124 21.9928Z"/>
        <path fill="white" d="M11.8128 31.4341C4.0829 36.861 -1.33876 44.9865 0.289958 46.9268C2.26953 49.2722 3.14483 46.0458 5.84827 49.157C8.55171 52.2682 5.56758 60.4977 12.0086 64.6608C18.8152 68.1957 24.3957 61.4827 28.4324 62.2782C32.4691 63.0736 30.1313 65.4526 33.1375 65.9952C35.612 66.4487 39.8925 57.6616 40.7013 48.2129C41.2996 41.2062 37.9092 36.2514 32.3583 32.6012C32.8827 33.8502 32.5909 36.3815 28.9236 42.0983C23.8047 50.0825 19.7976 53.2495 18.8669 52.6919C17.9362 52.1343 18.6453 47.0829 22.9553 38.6303C26.0428 32.5752 28.0704 31.0549 29.4111 30.8877C23.5019 27.888 17.541 27.4085 11.8128 31.4341Z"/>
      </svg>
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
      timeout: 125
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
          this.timeout += 125;
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
  $t-link-duration: 0.3s;
  $t-link-color: transparentize(#ffffff, .5);

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
      margin-right: auto;
      & path {
        transition: $t-link-duration;
      }
      &:hover > path{
        fill: $t-link-color !important;
        cursor: pointer;
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
        margin-left: 50px;
        letter-spacing: 0.06rem;
        &:first-child{
          margin-left: 0;
        }
        &:hover{ 
          cursor: pointer;
          color: $t-link-color;
        }
      }
    }
  }

  .t-stairs {
    transition: transform .5s ease-in-out, opacity 1s ease-in-out, color $t-link-duration ease-in-out;
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