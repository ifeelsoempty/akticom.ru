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
    magnetMove(e) {
      let target = e.target;
      let realTarget = target.closest('.cursor-magnet');

      if(target.classList.contains('cursor-magnet__trigger') || target.closest('.cursor-magnet')){
        let realTargetRect = realTarget.getBoundingClientRect();
        let transformY = (this.yChild - (realTargetRect.top + (realTargetRect.height / 2))) / 2;
        let transformX = (this.xChild - (realTargetRect.left + (realTargetRect.width / 2))) / 2;
  
        realTarget.style.transform = `translate(${transformX}px,${transformY}px)`
      }
    },

    magnetOut(e) {
      if(!e.relatedTarget.closest('.cursor-magnet') && e.target.closest('.cursor-magnet')){
        let realTarget = e.target.closest('.cursor-magnet');
        realTarget.style.transform = 'translate(0, 0)';
      }
    },

    overCursorTarget(e) {
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
      }
    },

    outCursorTarget(e) {
      const target = e.relatedTarget;
      if (target){
        e.target.removeEventListener('mouseover', this.overCursorTarget);
        const parent = target.closest('[data-cursor-type]');
        if(!parent){
          this.activeType = 'default';
        }
        e.target.removeEventListener('mouseout', this.outCursorTarget);
      }
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
    
    document.addEventListener('mouseover', this.overCursorTarget);
    document.addEventListener('mouseout', this.outCursorTarget);

    document.addEventListener('mousemove', this.magnetMove);
    document.addEventListener('mouseout', this.magnetOut);
  }
}
</script>