<template lang="pug">
.app-footer
  section-social
  .footbot: .footbot__container
    .footbot__brandmark
      img.footbot__img(src="~images/logos/eoscochain-brandmark.png")
    .footbot-menu
      .footbot-menu__title {{ $t('Foundation') }}
      .footbot-menu__items
        router-link(:to="{ name: 'about'}").footbot-menu__item {{ $t('About') }}
        router-link(:to="{ name: 'events'}").footbot-menu__item {{ $t('Events') }}
        router-link(:to="{ name: 'blog'}").footbot-menu__item {{ $t('Blog') }}
        // router-link(:to="{ name: 'assets'}").footbot-menu__item {{ $t('VisualAssets') }}
        // a(:href="urls.fundraiser" target="_blank").footbot-menu__item {{ $t('Fundraiser') }}
    .footbot-menu
      .footbot-menu__title {{ $t('Learn') }}
      .footbot-menu__items
        router-link(:to="{ name: 'resources'}").footbot-menu__item {{ $t('Resources') }}
        // router-link(:to="{ name: 'academy'}").footbot-menu__item {{ $t('Academy') }}
        router-link(:to="{ name: 'whitepaper'}").footbot-menu__item {{ $t('Whitepaper') }}
        router-link(:to="{ name: 'faq'}").footbot-menu__item {{ $t('FAQ') }}
    .footbot-menu
      .footbot-menu__title {{ $t('Develop') }}
      .footbot-menu__items
        a(href="https://github.com/eoscochain/eoscochain" target="_blank").footbot-menu__item EOS Cochain
        a(href="https://github.com/eoscochain/eos-contracts/tree/master/icp" target="_blank").footbot-menu__item 跨链合约
        a(href="https://github.com/eoscochain/eos-relay" target="_blank").footbot-menu__item 跨链中继
        // a(:href="urls.gh.cosmosSdk" target="_blank").footbot-menu__item Cosmos SDK
        // a(:href="urls.gh.voyager" target="_blank").footbot-menu__item {{ $t('Cosmos Voyager') }}
        // a(:href="urls.gh.tendermint" target="_blank").footbot-menu__item Tendermint Core
        // a(:href="urls.gh.lotion" target="_blank").footbot-menu__item {{ $t('Lotion') }}
</template>

<script>
import { mapGetters } from "vuex"
import SectionSocial from "sections/SectionSocial"
export default {
  name: "app-footer",
  components: {
    SectionSocial
  },
  computed: {
    ...mapGetters(["urls"])
  }
}
</script>

<style lang="stylus">
@require '~variables'

.app-footer
  background app-bg
  position relative
  z-index z(appMenu)

.footbot__container
  max-width 1024px
  margin 0 auto

.footbot
  background app-fg

.footbot__container
  display flex
  flex-flow row wrap
  max-width 1024px
  margin 0 auto

.footbot__brandmark
  padding 0
  flex 0 0 50%

.footbot__img
  max-width 50vw

.footbot-menu
  padding 1.5rem
  flex 0 0 50%

.footbot-menu__title
  color bright
  line-height 2rem

.footbot-menu__items
  display flex
  flex-flow column nowrap

.footbot-menu__item
  line-height 2rem

@media screen and (min-width: 768px)
  .footbot__container
    padding 3.5rem 0

  .footbot__brandmark
    flex 0 0 50%

  .footbot__img
    max-width 14rem

  .footbot-menu
    flex 0 0 16.66667%

  .footbot-menu__title
    margin-bottom 1rem
</style>
