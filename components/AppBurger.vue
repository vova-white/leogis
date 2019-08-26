<template>
  <b-button variant="link" class="burger" type="button">
    <MenuDefault width="33" />
  </b-button>
</template>

<script>
import MenuDefault from '~/assets/svg/MenuDefault.svg'
export default {
  components: {
    MenuDefault
  }
}
</script>

<style lang="scss">
.burger {
  width: width-scalable(66);
  padding: 0;
  @include media-breakpoint-up('lg') {
    width: width-scalable(19, $desktop-width);
  }
  svg path {
    fill: $white;
    transition: $transition-base;
  }
  &:hover {
    svg path {
      fill: $primary;
    }
  }
}
</style>
