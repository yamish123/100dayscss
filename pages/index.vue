<template>
  <div class="ly_container">
    <day-1 />
    <day-2 />
  </div>
</template>

<script lang="ts">
import { Component } from 'nuxt-property-decorator'
import Vue from 'vue'

@Component
export default class IndexPage extends Vue {}
</script>

<style lang="scss" scoped>
.ly_container {
  display: flex;
  flex-wrap: wrap;
  @apply p-8 -mt-4;

  > * {
    @apply mt-4 mr-4;
  }
}
</style>
