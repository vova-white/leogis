<template>
  <ul class="social">
    <li v-for="item in list" :key="item.index" class="social__item">
      <a
        :href="item.url"
        class="social__link"
        :title="item.class"
        target="_blank"
      >
        <component
          :is="item.icon"
          :width="item.width"
          :class="['icon', 'icon--' + item.class]"
        />
      </a>
    </li>
  </ul>
</template>

<script>
import Facebook from '~/assets/svg/Facebook.svg'
import Twitter from '~/assets/svg/Twitter.svg'
import Instagram from '~/assets/svg/Instagram.svg'

export default {
  data() {
    return {
      list: [
        { class: 'facebook', url: 'facebook.com', icon: Facebook, width: '10' },
        { class: 'twitter', url: 'facebook.com', icon: Twitter, width: '23' },
        {
          class: 'instagram',
          url: 'facebook.com',
          icon: Instagram,
          width: '21'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
$icons: (
  facebook: 20,
  twitter: 36,
  instagram: 40
);
$iconsDesktop: (
  facebook: 10,
  twitter: 24,
  instagram: 20
);
$iconsColors: (
  facebook: #4267b2,
  twitter: #1da1f2,
  instagram: #405de6
);
.social {
  margin: 0;
  padding: 0;
  list-style: none;
  display: flex;
  align-items: center;

  &__item:last-child {
    .social__link {
      padding-right: 0;
    }
  }

  &__link {
    display: block;
    padding: width-scalable(20) width-scalable(24);
    @include media-breakpoint-up('lg') {
      padding: width-scalable(10, $desktop-width)
        width-scalable(26, $desktop-width);
    }

    &:hover {
      @each $name, $color in $iconsColors {
        .icon--#{$name} path {
          fill: $color;
        }
      }
    }
  }

  .icon {
    @each $name, $size in $icons {
      &--#{$name} {
        width: width-scalable($size);
      }
    }
    @include media-breakpoint-up('lg') {
      @each $name, $size in $iconsDesktop {
        &--#{$name} {
          width: width-scalable($size, $desktop-width);
        }
      }
    }
    path {
      transition: $transition-base;
      fill: $white;
    }
  }
}
</style>
