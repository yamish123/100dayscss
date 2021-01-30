<template>
  <base-container title="Day1">
    <div class="day1">
      <div class="day1_menuIcon" :class="menuIconClass" @click="toggleActive">
        <div class="day1_menuIcon_line el_line1"></div>
        <div class="day1_menuIcon_line el_line2"></div>
        <div class="day1_menuIcon_line el_line3"></div>
      </div>
    </div>
  </base-container>
</template>

<script lang="ts">
import { Component } from 'nuxt-property-decorator'
import Vue from 'vue'

@Component
export default class Day1 extends Vue {
  isActive = false

  get menuIconClass() {
    return {
      active: this.isActive,
    }
  }

  toggleActive() {
    this.isActive = !this.isActive
  }
}
</script>

<style lang="scss" scoped>
.day1 {
  background: #3faf82;
  display: flex;
  justify-content: center;
  align-items: center;

  &_menuIcon {
    &_line {
      height: 8px;
      width: 80px;
      border-radius: 3px;
      box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.3);
      transition: background-color 0.2s ease-in-out;

      @apply bg-white;
    }

    &_line + &_line {
      margin-top: 14px;
    }

    &:hover {
      cursor: pointer;
    }

    .el_line1 {
      animation: animate-line-1-rev 0.7s ease-in-out;
    }

    .el_line2 {
      animation: animate-line-2-rev 0.7s ease-in-out;
    }

    .el_line3 {
      animation: animate-line-3-rev 0.7s ease-in-out;
    }

    &.active {
      .el_line1 {
        animation: animate-line-1 0.7s cubic-bezier(0.3, 1, 0.7, 1) forwards;
      }

      .el_line2 {
        animation: animate-line-2 0.7s cubic-bezier(0.3, 1, 0.7, 1) forwards;
      }

      .el_line3 {
        animation: animate-line-3 0.7s cubic-bezier(0.3, 1, 0.7, 1) forwards;
      }
    }
  }
}

@keyframes animate-line-1 {
  0% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }

  50% {
    transform: translate3d(0, 22px, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, 22px, 0) rotate(45deg);
  }
}
@keyframes animate-line-1-rev {
  0% {
    transform: translate3d(0, 22px, 0) rotate(45deg);
  }

  50% {
    transform: translate3d(0, 22px, 0) rotate(0);
  }

  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
}
@keyframes animate-line-2 {
  0% {
    transform: scale(1);
    opacity: 1;
  }

  100% {
    transform: scale(0);
    opacity: 0;
  }
}
@keyframes animate-line-2-rev {
  0% {
    transform: scale(0);
    opacity: 0;
  }

  100% {
    transform: scale(1);
    opacity: 1;
  }
}
@keyframes animate-line-3 {
  0% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }

  50% {
    transform: translate3d(0, -22px, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, -22px, 0) rotate(135deg);
  }
}
@keyframes animate-line-3-rev {
  0% {
    transform: translate3d(0, -22px, 0) rotate(135deg);
  }

  50% {
    transform: translate3d(0, -22px, 0) rotate(0);
  }

  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
}
</style>
