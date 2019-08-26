<template>
  <div class="section features">
    <b-row align-h="around">
      <b-col
        v-for="item in features"
        :key="item.index"
        cols="auto"
        class="features__item"
      >
        <div class="features__icon">
          <component :is="item.icon" :class="['icon', 'icon--' + item.class]" />
        </div>
        <h4 class="features__title">
          {{ item.text }}
        </h4>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import Location from '~/assets/svg/IconsLocation.svg'
import Apps from '~/assets/svg/IconsApps.svg'
import Hands from '~/assets/svg/IconsHands.svg'
export default {
  data() {
    return {
      features: [
        { icon: Location, text: 'Arbeiten von überall aus', class: 'location' },
        { icon: Apps, text: 'Apps einfach buchen & nutzen', class: 'apps' },
        { icon: Hands, text: 'Monatlicher festreis', class: 'hands' }
      ]
    }
  }
}
</script>

<style lang="scss">
.features {
  background: $gray-100;
  padding: width-scalable(180) width-scalable(54);
  @include media-breakpoint-up('xl') {
    background: $primary;
    padding: width-scalable(92, $desktop-width)
      width-scalable(100, $desktop-width);
  }

  &__item {
    text-align: center;
  }

  &__icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: width-scalable(185);
    height: width-scalable(185);
    margin: 0 auto width-scalable(55);
    border-radius: 50%;
    background: $white;
    border: 1px solid $primary;
    @include media-breakpoint-up('xl') {
      width: width-scalable(122, $desktop-width);
      height: width-scalable(122, $desktop-width);
      margin: 0 auto width-scalable(36, $desktop-width);
    }

    $features: (
      location: 115,
      apps: 80,
      hands: 105
    );
    $featuresDesktop: (
      location: 78,
      apps: 54,
      hands: 70
    );
    @each $name, $size in $features {
      .icon--#{$name} {
        width: width-scalable($size);
      }
    }
    @include media-breakpoint-up('xl') {
      @each $name, $size in $featuresDesktop {
        .icon--#{$name} {
          width: width-scalable($size, $desktop-width);
        }
      }
    }
  }
  &__title {
    width: width-scalable(280);
    margin: 0 auto;
    @include media-breakpoint-up('xl') {
      color: $white;
      width: width-scalable(180, $desktop-width);
    }
  }
}
</style>
