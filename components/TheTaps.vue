<template>
  <div class="taps">
    <div class="taps__inner">
      <div class="taps__shape" />
      <b-row v-for="item in taps" :key="item.index" class="tap">
        <b-col cols="6" class="section tap__content">
          <h3 class="tap__title">
            {{ item.title }}
          </h3>
          <p class="tap__text">
            <span class="d-lg-none d-lg-none">{{ item.mobileText }}</span>
            <span class="d-none d-lg-inline">{{ item.text }}</span>
          </p>
          <b-button variant="outline-dark" class="d-lg-none">
            Mehr
          </b-button>
        </b-col>
        <b-col cols="6" class="tap__picture">
          <picture>
            <source
              media="(max-width: 767px)"
              :srcset="
                `${require(`~/assets/${item.img}@1x.jpg`)} 2x, ${require(`~/assets/${item.img}@0,5x.jpg`)} 1x`
              "
            />
            <source
              media="(max-width: 1599px)"
              :srcset="
                `${require(`~/assets/${item.img}@2x.jpg`)} 2x, ${require(`~/assets/${item.img}@1x.jpg`)} 1x`
              "
            />
            <source
              media="(min-width: 1600px)"
              :srcset="`${require(`~/assets/${item.img}@2x.jpg`)}`"
            />
            <img
              :src="require(`~/assets/${item.img}@0,5x.jpg`)"
              :alt="item.title"
            />
          </picture>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      taps: [
        {
          img: 'images/tap__img--0',
          title: 'Dein Gerät ist Dein Büro.',
          text:
            'Mit Leogis ist es egal, von wo aus Du arbeitest. Denn so lange Du mit dem Internet verbunden bist, bist Du auch mit Deinem Team verbunden. Alle Daten werden zudem immer mit Deiner Cloud synchron gehalten. So arbeitest Du nicht nur aktuell, sondern auch sicher.',
          mobileText: 'Lorum ipsum ist die Basis. Komplettes Logis IT-paket.'
        },
        {
          img: 'images/tap__img--1',
          title: 'Mühelos sicher & immer up-to-date.',
          text:
            'Das Leogis App & Device Management kümmert sich um alles: Installationen und Deinstallation von Apps, Datensicherung und Updates. Zudem werden alle Deine Einstellungen in der Leogis Cloud synchron gehalten, was den Wechsel eines Geräts – auch bei Verlust –  jederzeit unkompliziert möglich macht.',
          mobileText: 'Lorum ipsum ist die Basis. Komplettes Logis IT-paket.'
        },
        {
          img: 'images/tap__img--2',
          title: 'Apps so einfach wie noch nie.',
          text:
            'Du kennst das: Installationen von Apps oder Treibern können manchmal ganz schön anstrengend sein. Bei Leogis steuerst Du alles über unser App Center. Einfach App oder ein von Leogis angebotenes Zusatzgerät wie Drucker anschließen, markieren und die Installation läuft voll automatisiert, natürlich inklusive Updates.',
          mobileText: 'Lorum ipsum ist die Basis. Komplettes Logis IT-paket.'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.taps {
  @include media-breakpoint-up('lg') {
    width: 100%;
    max-width: $wrapper-width;
    padding-top: 100%;
    overflow: hidden;
    position: relative;
    &__inner {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      z-index: 1;
    }
    &__shape {
      position: absolute;
      width: 100%;
      height: 100%;
      z-index: 1;
      opacity: 0.4;
      top: 0;
      left: 0;
      &::before,
      &::after {
        content: '';
        position: absolute;
        display: block;
      }
      &::before {
        width: 100%;
        height: 100%;
        background-image: linear-gradient(
          -87deg,
          rgba(0, 0, 0, 1) 0%,
          rgba(255, 255, 255, 0) 100%
        );
        z-index: 1;
      }
      &::after {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border: width-scalable(300, $desktop-width) solid rgba($primary, 0.5);
        z-index: 2;
      }
    }
  }
}
.tap {
  &__picture {
    img {
      height: 100%;
      object-fit: cover;
    }
  }

  &:nth-child(odd) {
    .tap__content {
      order: 2;
    }
  }

  &__text {
    margin-bottom: 88/ ($font-size-base) * 1em;
  }

  @include media-breakpoint-up('lg') {
    height: 33.33333vw;
    position: relative;

    &:nth-child(odd) {
      .tap__content {
        order: 0;
      }
    }
    &:nth-child(even) {
      .tap__content {
        order: 2;
      }
    }

    &__title {
      width: 74%;
    }

    &__content {
      position: relative;
      padding-top: 0;
      padding-bottom: 0;
      display: flex;
      align-content: center;
      flex-wrap: wrap;
      z-index: 5;
      background: $white;
    }

    &__text {
      margin-bottom: 0;
    }
  }
}
// .wrapper {
//   width: 100vw;
//   height: 100vw;
//   overflow: hidden;
//   position: relative;
// }
// .shape {
//   position: absolute;
//   width: 100%;
//   height: 100%;
//   z-index: 1;
//   opacity: 0.4;
// }

// .shape:before {
//   content: '';
//   position: absolute;
//   display: block;
//   width: 100%;
//   height: 100%;
//   background-image: linear-gradient(
//     -87deg,
//     rgba(0, 0, 0, 1) 0%,
//     rgba(255, 255, 255, 0) 100%
//   );
//   z-index: 1;
// }

// .shape:after {
//   content: '';
//   position: absolute;
//   display: block;
//   width: 100vw - (600/1280 * 100vw);
//   height: 100vw - (600/1280 * 100vw);
//   border-radius: 50%;
//   top: 50%;
//   left: 50%;
//   transform: translate(-50%, -50%);
//   border: (300/1280 * 100vw) solid #2699fb;
//   z-index: 2;
// }

// .row {
//   display: flex;
// }

// .col {
//   width: 50%;
//   height: 33.33333vw;
//   &--right {
//     position: relative;
//     background: #fff;
//     z-index: 3;
//   }
// }

// img {
//   width: 100%;
//   height: 100%;
//   object-fit: cover;
// }
</style>
