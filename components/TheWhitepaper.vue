<template>
  <section>
    <b-row>
      <b-col cols="12" sm="6" class="section">
        <b-row>
          <b-col cols="10">
            <h2 class="whitepaper__title">
              Wer sagt, das IT schwer sein muss.
            </h2>
            <p class="font-weight-medium">
              Unser Whitepaper verrät Ihnen:
            </p>
            <ul class="whitepaper__list">
              <li>
                Wie Sie als kleines Unternehmen schnellund einfach eine moderne
                IT Infrastrukturaufbauenz
              </li>
              <li>Mit welchen Kosten Sie rechnen müssen</li>
              <li>
                Wie Sie von den neuenMöglichkeiten des modernen Arbeitens
                profitieren
              </li>
            </ul>
            <b-button variant="outline-secondary">
              Zum Whitepaper
            </b-button>
          </b-col>
        </b-row>
      </b-col>
      <b-col cols="12" sm="6">
        <picture class="whitepaper__picture">
          <source
            media="(max-width: 767px)"
            :srcset="
              `${require(`~/assets/images/whitepaper__img@1x.jpg`)} 2x, ${require(`~/assets/images/whitepaper__img@0,5x.jpg`)} 1x`
            "
          />
          <source
            media="(max-width: 1599px)"
            :srcset="
              `${require(`~/assets/images/whitepaper__img@2x.jpg`)} 2x, ${require(`~/assets/images/whitepaper__img@1x.jpg`)} 1x`
            "
          />
          <source
            media="(min-width: 1600px)"
            :srcset="`${require(`~/assets/images/whitepaper__img@2x.jpg`)}`"
          />
          <img
            src="~/assets/images/whitepaper__img@0,5x.jpg"
            alt="Wer sagt, das IT schwer sein muss."
          />
        </picture>
      </b-col>
    </b-row>
  </section>
</template>

<style lang="scss">
.whitepaper {
  &__title {
    padding-right: 20%;
  }

  &__list {
    margin-bottom: width-scalable(60, $desktop-width);
  }

  &__picture {
    img {
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
