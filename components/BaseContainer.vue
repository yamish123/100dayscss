<template>
  <div class="bl_container">
    <div class="bl_container_header">
      {{ title }}
    </div>
    <div class="bl_container_body">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component, Prop } from 'nuxt-property-decorator'

@Component
export default class BaseContainer extends Vue {
  @Prop({ type: String, default: '' })
  title!: string
}
</script>

<style lang="scss" scoped>
.bl_container {
  color: #333;

  &_header {
    @apply font-medium;
  }

  &_body {
    @apply mt-2;

    width: 400px;
    height: 400px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 2px;
    box-shadow: 4px 8px 16px 0 rgba(0, 0, 0, 0.1);

    > * {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
