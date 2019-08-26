<template>
  <footer class="footer section section--dark">
    <b-row class="d-lg-none" align-h="between">
      <b-col cols="7">
        <h3>Stay in touch for fresh products!</h3>
      </b-col>
      <b-col cols="auto">
        <AppSocial />
      </b-col>
    </b-row>
    <b-row class="d-lg-none" align-h="between" align-v="end">
      <b-col>
        <ul class="footer-menu">
          <li
            v-for="item in mobileMenu"
            :key="item.index"
            class="footer-menu__item"
          >
            <a href="#0" class="footer-menu__link" :title="item">{{ item }}</a>
          </li>
        </ul>
      </b-col>
      <b-col cols="auto">
        <b-button variant="outline-light" class="footer__btn">
          Kontakt
        </b-button>
      </b-col>
    </b-row>

    <b-row class="d-none d-lg-flex footer__row">
      <b-col cols="3">
        <Logo width="86" class="footer__logo" />
      </b-col>
      <b-col cols="6">
        <div class="contacts">
          <a href="mailto:info@leogis.de" class="h2 contacts__link">
            info@leogis.de
          </a>
          <a href="tel:0228243444" class="h2 contacts__link">0228243444</a>
        </div>
      </b-col>
    </b-row>
    <b-row class="d-none d-lg-flex">
      <b-col cols="3" offset-lg="3">
        <div class="address">
          &copy;2019 Leogis GmbH
          <br />Fritz-Schäffer-Straße 1 <br />53113 Bonn <br />Germany
        </div>
      </b-col>
      <b-col cols="3">
        <ul class="footer__menu">
          <li>
            <a href="#0" class="footer__link" title="Datenschutz">
              Datenschutz
            </a>
          </li>
          <li>
            <a href="#0" class="footer__link" title="Datenschutz">
              Privatphäre
            </a>
          </li>
          <li>
            <a href="#0" class="footer__link" title="Datenschutz">Impressum</a>
          </li>
        </ul>
      </b-col>
      <b-col cols="3">
        <AppSocial />
      </b-col>
    </b-row>
  </footer>
</template>

<script>
import Logo from '~/assets/svg/Logo.svg'
import AppSocial from '~/components/AppSocial'
export default {
  components: {
    Logo,
    AppSocial
  },
  data() {
    return {
      mobileMenu: ['Vorteile', 'Whitepaper', 'Beratung', 'Kontakt']
    }
  }
}
</script>

<style lang="scss">
.footer {
  &-menu {
    padding: 0;
    margin: 0;
    list-style: none;

    &__link {
      color: $white;
    }
  }

  &__btn {
    position: relative;
    top: width-scalable(-10);
  }

  @include media-breakpoint-up('lg') {
    &__row {
      margin-bottom: width-scalable(56, $desktop-width);
    }
    &__logo {
      width: width-scalable(86, $desktop-width);
      path {
        fill: $white;
      }
    }

    .address,
    &__menu {
      font-size: width-scalable(12, $desktop-width);
      @include emLh(22, 12);
    }
    &__menu {
      list-style: none;
      margin: 0;
      padding: 0;
    }
    &__link {
      color: $white;
    }
  }
}

.contacts {
  position: relative;
  top: width-scalable(-13, $desktop-width);
  &__link {
    color: $white;
    margin-bottom: 0;
  }
}
</style>
