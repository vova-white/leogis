<template>
  <div class="promo">
    <div class="promo__bg">
      <div class="shape" />
    </div>
    <div class="section promo__content">
      <b-row align-v="end">
        <b-col cols="12" lg="6">
          <h1 class="promo__title">
            Mehr Zeit für das, was wirklich zum Job gehört.
          </h1>
          <b-row align-v="end">
            <b-col cols="12" md="7" class="promo__text h4">
              das rundum-sorglos-abo<br />für it ab € 79,00 / monat
            </b-col>
            <b-col cols="12" md="5" class="promo__button">
              <b-button variant="outline-light">
                Los geht’s
              </b-button>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<style lang="scss">
.promo {
  position: relative;
  &__bg {
    position: relative;
    height: width-scalable(1020);
    background: url('~assets/images/promo__bg@0,25x.jpg') no-repeat 100% 50%;
    background-size: cover;
    overflow: hidden;
    &::before {
      content: '';
      position: absolute;
      display: block;
      width: 100%;
      height: 100%;
      opacity: 0.4;
      background-image: linear-gradient(
        45deg,
        rgba(0, 0, 0, 1) 0%,
        rgba(0, 0, 0, 0) 100%
      );
      z-index: 1;
    }
    @include resolution {
      background-image: url('~assets/images/promo__bg@0,5x.jpg');
    }
    @include media-breakpoint-up('md') {
      height: 100vh;
      background-position: center;
      background-image: url('~assets/images/promo__bg@0,5x.jpg');
      @include resolution {
        background-image: url('~assets/images/promo__bg@0,75x.jpg');
      }
    }
    @include media-breakpoint-up('lg') {
      height: 100vh;
      min-height: width-scalable(700, $desktop-width, 'vw');
    }
    @include media-breakpoint-up('xl') {
      background-image: url('~assets/images/promo__bg@0,75x.jpg');
      @include resolution {
        background-image: url('~assets/images/promo__bg.jpg');
      }
    }
    @include media-breakpoint-up('xxl') {
      background-image: url('~assets/images/promo__bg.jpg');
    }
  }

  &__content {
    background: $primary;
    color: $white;
    @include media-breakpoint-up('md') {
      position: absolute;
      top: 0;
      height: 100%;
      display: flex;
      align-items: flex-end;
      background: transparent;
      z-index: 5;
    }
  }

  &__title {
    padding-right: width-scalable(120);
    @include media-breakpoint-up('lg') {
      padding-right: width-scalable(155, $desktop-width);
    }
  }

  &__text {
    margin-bottom: 48 / ($h4-font-size) * 1em;
    @include media-breakpoint-up('md') {
      margin-bottom: 0;
    }
  }

  &__button {
    text-align: right;
  }
}

.shape {
  position: absolute;
  z-index: 1;
  opacity: 0.5;
  top: 83%;
  width: width-scalable(2000);
  height: width-scalable(1000);
  box-sizing: border-box;
  overflow: hidden;
  @include media-breakpoint-up('lg') {
    top: 50%;
    width: width-scalable(1760, $desktop-width);
    height: width-scalable(1760, $desktop-width);
  }
  &:after {
    content: '';
    position: absolute;
    display: block;
    width: width-scalable(2000);
    height: width-scalable(2000);
    top: -7%;
    border-radius: 50%;
    border: width-scalable(456) solid rgba($primary, 0.5);
    z-index: 2;
    @include media-breakpoint-up('lg') {
      top: 29%;
      width: width-scalable(1760, $desktop-width);
      height: width-scalable(1760, $desktop-width);
      border-width: width-scalable(414, $desktop-width);
    }
  }
  &,
  &:after {
    left: 50%;
    transform: translate(-50%, -50%);
  }
}
</style>
