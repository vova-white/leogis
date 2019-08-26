<template>
  <section class="updates section section--light">
    <b-row>
      <b-col cols="6" md="12" lg="6">
        <h2 class="h2--line_small updates__title col-md-6 col-lg-10">
          Genial einfach: Alles zum Losstarten aus einer Hand.
        </h2>
        <b-row>
          <b-col cols="12" md="6">
            <p class="updates__text">
              Endlich unabhängig.<br />
              Hardware und Sofatware immer sicher und up to date.
            </p>
            <b-button variant="outline-primary">
              Geräte & Apps
            </b-button>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </section>
</template>

<style lang="scss">
.updates {
  background-image: url('~assets/images/updates__bg@0,25x.png');
  background-repeat: no-repeat;
  background-position: 60% 90%;
  background-size: width-scalable(900) auto;
  padding-bottom: width-scalable(466);
  @include resolution {
    background-image: url('~assets/images/updates__bg@0,5x.png');
  }
  @include media-breakpoint-up('md') {
    background-image: url('~assets/images/updates__bg@0,5x.png');
    @include resolution {
      background-image: url('~assets/images/updates__bg@0,75x.png');
    }
  }
  @include media-breakpoint-up('lg') {
    padding-bottom: width-scalable(100, $desktop-width);
    background-size: width-scalable(780, $desktop-width) auto;
    background-position: 85% 85%;
  }
  @include media-breakpoint-up('xl') {
    background-image: url('~assets/images/updates__bg@0,75x.png');
    @include resolution {
      background-image: url('~assets/images/updates__bg.png');
    }
  }
  @include media-breakpoint-up('xxl') {
    background-image: url('~assets/images/updates__bg.png');
  }
  &__text {
    margin-bottom: 88/ ($font-size-base) * 1em;
  }
}
</style>
