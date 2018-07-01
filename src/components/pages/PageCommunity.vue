<template lang="pug">
page.page-community(
  :title="$t('Community')"
  :subtitle="$t('These are the only official EOS Cochain communication channels.')")

  part(:title="$t('Chat')"): .community-cards
    card-social(
      dt="Wechat"
      dd="Add the secretary to join us on Wechat : jimlucky008"
      icon-type="mi"
      icon="chat")
    card-social(
      dt="QQ"
      dd="Join us on QQ Grop : 721739777"
      icon-type="mi"
      icon="chat")
    card-social(
      dt="Telegram Chinese Channel"
      dd="Join us on Telegram"
      icon="telegram"
      anchor="https://t.me/EOSCochainProject")
    card-social(
      dt="Telegram English Channel"
      dd="Join us on Telegram"
      icon="telegram"
      anchor="https://t.me/EOSCochainEn")
    card-social(
      dt="Weibo"
      dd="Focus on us on Weibo"
      icon-type="mi"
      icon="chat"
      anchor="https://www.weibo.com/eoscochain")
  // part(:title="$t('Forums')"): .community-cards
    card-social(
      dt="WeChat Admin Platform"
      dd="Subscribe to /r/cosmosnetwork"
      icon="weChat"
      :anchor="links.cosmos.community.reddit")
      part(title="Social Media"): .community-cards
    card-social(
      dt="Twitter"
      dd="Follow @cosmos, our official account"
      icon="twitter"
      :anchor="links.cosmos.community.twitter")
    card-social(
      dt="Medium"
      dd="Read the latest on the Cosmos Blog"
      icon="medium"
      :anchor="links.cosmos.blog")
    card-social(
      dt="YouTube"
      dd="Watch videos on our official channel"
      icon="youtube"
      anchor="https://www.youtube.com/c/CosmosProject")
</template>

<script>
import { mapGetters } from "vuex"
import CardSocial from "cards/CardSocial"
import Page from "common/NiPage"
import Part from "common/NiPart"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-community",
  metaInfo: { title: "Community" },
  components: {
    CardSocial,
    Part,
    Page,
    TextContainer
  },
  computed: {
    ...mapGetters(["links"])
  }
}
</script>

<style lang="stylus">
@require '~variables'

@media screen and (min-width: 768px)
  .page-community .community-cards
    display flex
    flex-flow row wrap

    .ni-card-social
      flex 0 0 50%
</style>
