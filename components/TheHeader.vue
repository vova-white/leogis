<template>
  <header class="section header">
    <app-logo />
    <the-menu />
  </header>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import TheMenu from '~/components/TheMenu.vue'

export default {
  components: {
    AppLogo,
    TheMenu
  }
}
</script>

<style lang="scss">
.header {
  padding-top: width-scalable(88);
  padding-bottom: 0;
  position: absolute;
  width: 100%;
  z-index: 500;
  display: flex;
  justify-content: space-between;
  align-items: center;
  @include media-breakpoint-up('lg') {
    padding: width-scalable(44, $desktop-width)
      width-scalable(44, $desktop-width) 0;
  }
}
</style>
