<template>
  <div class="accordion">
    <div class="accordion-title" @click="open()">
      <slot name="title"></slot>
      <transition name="rotate" mode="out-in">
        <i class="fas fa-chevron-up" v-if="isOpen" key="rotate1">
          <img src="~/static/images/AccordionMenu/menu_arrow.svg" width="25px" height="25px" alt="">
        </i>
        <i class="fas fa-chevron-down" v-else key="rotate2">
          <img src="~/static/images/AccordionMenu/menu_arrow.svg" width="25px" height="25px" alt="">
        </i>
      </transition>
    </div>
    <transition name="open">
      <div class="accordion-content" v-if="isOpen">
        <slot name="content"></slot>
      </div>
    </transition>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data(){
    return {
      isOpen: false as Boolean
    }
  },
  methods: {
    open: function () {
      this.isOpen = !this.isOpen;
    }
  },
})
</script>

<style lang="scss" scoped>
.accordion {
  width: 310px;
  height: 630px;
  &-title {
    width: 100%;
    height: 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
  }
}
@keyframes open {
  0% {
    opacity: 0;
    transform: translateY(-5px);
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
}
.open-enter-active {
  animation: open .2s;
}
.open-leave-active {
  animation: open .2s linear reverse;
}

@keyframes rotate {
  0% {
    transform: rotate(180deg);
  }
}
.rotate-enter-active {
  animation: rotate .2s linear;
}
</style>
