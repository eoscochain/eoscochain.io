<template lang='pug'>
.section-why
  .section-home.section-home-benefits: .section-home__container
    .section-home__header {{ $t('WhyUseEOSCochain') }}
    .section-home__main
      .cosmos-panels
        .cosmos-panel
          .cosmos-panel__image
            img.cosmos-panel__img(
              src="images/diagrams/panel-interoperability.png")
          .cosmos-panel__text
            .cosmos-panel__title {{ $t('Interoperable') }}
            .cosmos-panel__body {{ $t('InteroperableDescription') }}
            .cosmos-panel__action
              router-link(:to="{ name: 'intro'}") Interblockchain Comms &rsaquo;

        .cosmos-panel
          .cosmos-panel__image
            img.cosmos-panel__img(
              src="images/diagrams/panel-scalability.png")
          .cosmos-panel__text
            .cosmos-panel__title {{ $t('Scalable') }}
            .cosmos-panel__body {{ $t('ScalableDescription') }}
            .cosmos-panel__action
              router-link(:to="{ name: 'scaling-eth'}") Scaling Ethereum &rsaquo;

        .cosmos-panel
          .cosmos-panel__image
            img.cosmos-panel__img(
              src="images/diagrams/panel-developer-friendly.png")
          .cosmos-panel__text
            .cosmos-panel__title {{ $t('DeveloperFriendly') }}
            .cosmos-panel__body  {{ $t('DeveloperFriendlyDescription') }}
            .cosmos-panel__action
              router-link(:to="{ name: 'developers'}") Cosmos for Developers &rsaquo;
</template>

<script>
export default {
  name: "section-benefits"
}
</script>

<style lang="stylus">
@require '~variables'
.section-why
  background-image: linear-gradient(to bottom, app-bg, app-bg-hover);

.cosmos-panels
  margin 0 -1rem

.cosmos-panel
  background app-fg
  display flex
  flex-flow column nowrap
  margin 1rem

  &:first-child
    margin-top 0

  &:last-child
    margin-bottom 0

.cosmos-panel__title
.cosmos-panel__body
.cosmos-panel__action
  padding 1rem

.cosmos-panel__title + .cosmos-panel__body
  padding-top 0

.cosmos-panel__body + .cosmos-panel__action
  padding-top 0

.cosmos-panel__title
  color bright
  font-size h2
  font-weight 500

.cosmos-panel__img
  width 100%

.cosmos-panel__action
  display block

@media screen and (min-width: 768px)
  .cosmos-panel
    flex-flow row nowrap

  .cosmos-panel__image
    flex 1

  .cosmos-panel__text
    flex 2

  .cosmos-panel__title
  .cosmos-panel__body
  .cosmos-panel__action
    padding 1.5rem

@media screen and (min-width: 1024px)
  .cosmos-panels
    display flex
    flex-flow row nowrap

  .cosmos-panel
    flex 1
    flex-flow column nowrap
    display block
    &:first-child
    &:last-child
      margin 1rem

  .cosmos-panel__text
    display flex
    flex-flow column

  .cosmos-panel__body
    flex 1
    height 11rem
</style>
