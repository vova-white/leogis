<template>
  <div class="page-wrapper">
    <TheHeader />
    <b-row tag="main">
      <b-col cols="12">
        <ThePromo />
      </b-col>
      <b-col cols="12">
        <TheFeatures />
      </b-col>
      <b-col cols="12" class="d-none d-lg-block">
        <TheServices />
      </b-col>
      <b-col cols="12" order="1" order-lg="3">
        <TheDevices />
      </b-col>
      <b-col cols="12" order="2">
        <TheTaps />
      </b-col>
      <b-col cols="12" order="4">
        <TheUpdates />
      </b-col>
      <b-col cols="12" order="5" class="d-none d-lg-block">
        <TheSubscribe />
      </b-col>
      <b-col cols="12" order="6" class="d-none d-lg-block">
        <TheWhitepaper />
      </b-col>
      <b-col cols="12" order="7">
        <TheFooter />
      </b-col>
    </b-row>
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader.vue'
import ThePromo from '~/components/ThePromo'
import TheFeatures from '~/components/TheFeatures'
import TheServices from '~/components/TheServices'
import TheTaps from '~/components/TheTaps'
import TheDevices from '~/components/TheDevices'
import TheUpdates from '~/components/TheUpdates'
import TheSubscribe from '~/components/TheSubscribe'
import TheWhitepaper from '~/components/TheWhitepaper'
import TheFooter from '~/components/TheFooter'

export default {
  components: {
    TheHeader,
    ThePromo,
    TheFeatures,
    TheServices,
    TheTaps,
    TheDevices,
    TheUpdates,
    TheSubscribe,
    TheWhitepaper,
    TheFooter
  }
}
</script>

<style></style>
