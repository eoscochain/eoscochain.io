<template lang="pug">
page(:title="$t('What is EOS Cochain?')"
     :subtitle="$t('Get started with an overview of the EOS Cochain parachain.')")
  div(slot="menu"): btn(icon="chat" :value="$t('CommunityChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
  // text-container(url="https://api.github.com/repos/tendermint/aib-data/contents/md/intro-index.md")
  text-container(url="intro-index.md")
  text-container
    h4 {{ $t('Next') }}&hellip;
    // btn(value="Introduction to Cosmos Hub" type="link" :to="{ name: 'intro-hub' }" icon="chevron_right" icon-pos="right" color="primary" size="lg")
    btn(:value="$t('GoingFurther')" type="link" :to="{ name: 'intro-further' }" icon="chevron_right" icon-pos="right" color="primary" size="lg")
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-intro",
  metaInfo: { title: "Overview - Intro" },
  components: {
    Btn,
    Page,
    TextContainer
  }
}
</script>
