<template>
  <div ref="point" 
      :style="cursorPoint"
      :class="[ 
        'g-cursor', 
        `g-cursor_${activeType}`,
        { 'g-cursor_hide': hideCursor },
        ]"
      >
    <div class="g-cursor__point"></div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      xChild: 0,
      yChild: 0,
      hover: false,
      hideCursor: true,
      activeType: 'default',
      maxSize: 100,
      cursorTypes: {
        'default': {
          zoom: 0.1,
          width: 10,
          height: 10,
          center: 5,
        },
        'medium': {
          zoom: 0.5,
          center: 25,
        }
      }
    }
  },
  computed: {
    cursorPoint() {
      return `top: ${this.yChild - this.maxSize / 2}px; left: ${this.xChild - this.maxSize / 2}px`
    }
  },
  methods: {
    moveCursor(e) {
      this.xChild = e.clientX
      this.yChild = e.clientY;
    },
    handleCursorTarget() {
      document.addEventListener('mouseover', e => {
        const target = e.target;
        if (target){
          const cursorType = target.dataset.cursorType;
          const parent = target.closest('[data-cursor-type]');
          if(cursorType){
            this.activeType = cursorType
          } else if (parent){
            this.activeType = parent.dataset.cursorType;
          } else {
            this.activeType = 'default';
          }
  
          target.addEventListener('mouseout', e => {
            const target = e.relatedTarget;
            if (target){
              const parent = target.closest('[data-cursor-type]');
              if(!parent){
                this.activeType = 'default';
              }
            }
          })
        }
      })
    }
  },
  mounted() {
    document.addEventListener("mousemove", this.moveCursor);
    document.addEventListener('mouseleave', e => {
      this.hideCursor = true;
    });
    document.addEventListener('mouseenter', e => {
      this.hideCursor = false;
    });
    this.handleCursorTarget();
  }
}
</script>

<style lang="scss">
.g-cursor {
    position: fixed;
    width: 100px;
    height: 100px;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    mix-blend-mode: exclusion;
    pointer-events: none;
    user-select: none;
    backface-visibility: hidden;
    z-index: 99999999;

    &_hide {
      opacity: 0;
      transition: width .6s ease,
      height .6s ease,
      opacity .6s ease;
    }

    &__point {
      background: #fff;
      border-radius: 100%;
      backface-visibility: hidden;
      will-change: transform;
      transition: .3s height, .3s width;
    }

    &_medium {
      & .g-cursor__point{
        height: 50px;
        width: 50px;
      }
    }
    &_large {
      & .g-cursor__point{
        height: 100px;
        width: 100px;
      }
    }
    &_default {
      & .g-cursor__point{
        height: 10px;
        width: 10px;
      }
    }
    &_hidden {
      & .g-cursor__point{
        display: none;
      }
    }
    &_small {
      & .g-cursor__point{
        height: 25px;
        width: 25px;
      }
    }
  }
</style>