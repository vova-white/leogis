<template>
  <router-link to="/" class="logo" title="Leogis">
    <Leogis width="165" />
  </router-link>
</template>

<script>
import Leogis from '~/assets/svg/Leogis.svg'
export default {
  components: {
    Leogis
  }
}
</script>

<style lang="scss">
.logo {
  width: width-scalable(330);
  @include media-breakpoint-up('lg') {
    width: width-scalable(118, $desktop-width);
  }
  svg path {
    fill: #fff;
    transition: $transition-base;
  }

  &:hover {
    svg path {
      fill: $primary;
    }
  }
}
</style>
