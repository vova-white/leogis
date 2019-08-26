<template>
  <div fluid class="section section--light services">
    <b-row>
      <b-col cols="6">
        <h2 class="services__title">
          IT. So einfach, dass sie glücklich macht.
        </h2>
      </b-col>
      <b-col cols="6">
        <b-row>
          <b-col cols="9" class="services__content">
            <p class="services__text">
              Egal, ob Sie im Home-Office arbeiten, selbstständig tätig sind
              oder beruflich viel reisen: Mit Leogis sind Sie immer aktuell
              unterwegs – dank der neusten Geräten und der besten Software. Vom
              Laptop über das Tablet bis hin zum Surface bekommen Sie bei uns
              genau das, was Sie brauchen. Alles ausgestattet mit dem
              aktuellsten Windows und Office.
            </p>
            <p class="services__text font-weight-medium">
              Unsere Services:
            </p>
            <b-row class="services-list" align-v="center">
              <div
                v-for="item in services"
                :key="item.index"
                class="services-list__item"
              >
                <b-button
                  :id="`popover-${item.class}`"
                  class="services-list__popover"
                  variant="link"
                >
                  <component
                    :is="item.icon"
                    :width="item.width"
                    :class="['icon', 'icon--' + item.class]"
                  />
                </b-button>
                <b-popover
                  :target="`popover-${item.class}`"
                  placement="lefttop"
                  triggers="hover focus"
                  :content="item.popover"
                  custom-class="text-center"
                />
              </div>
            </b-row>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import IconsAdding from '@/assets/svg/IconsAdding.svg'
import IconsBox from '@/assets/svg/IconsBox.svg'
import IconsCloud from '@/assets/svg/IconsCloud.svg'
import IconsSecurity from '@/assets/svg/IconsSecurity.svg'

export default {
  components: {
    IconsAdding
  },
  data() {
    return {
      services: [
        {
          icon: IconsAdding,
          popover:
            'Alle ihre Einstellungen werden in der Leogis Cloud gesichert',
          class: 'adding',
          width: 35
        },
        {
          icon: IconsBox,
          popover:
            'Alle ihre Einstellungen werden in der Leogis Cloud gesichert',
          class: 'box',
          width: 36
        },
        {
          icon: IconsCloud,
          popover:
            'Alle ihre Einstellungen werden in der Leogis Cloud gesichert',
          class: 'cloud',
          width: 44
        },
        {
          icon: IconsSecurity,
          popover:
            'Alle ihre Einstellungen werden in der Leogis Cloud gesichert',
          class: 'security',
          width: 28
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.services {
  &__title {
    width: 80%;
  }

  &__content {
    padding-top: width-scalable(70, $desktop-width);
  }

  &-list {
    &__item {
      margin-right: width-scalable(44, $desktop-width);
    }

    &__popover {
      padding: 0;
    }

    $services: (
      adding: 35,
      box: 36,
      cloud: 44,
      security: 28
    );
    @each $name, $size in $services {
      .icon--#{$name} {
        width: width-scalable($size, $desktop-width);
      }
    }
  }
}
</style>
