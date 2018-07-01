<template lang="pug">
page(
  :title="$t('EOSCochainFAQ')"
  :subtitle="$t('Answers to frequently asked questions about the EOS Cochain Network.')")
  div(slot="menu"): btn(icon="chat" :value="$t('CommunityChat')" type="anchor" href="https://riot.im/app/#/group/+cosmos:matrix.org" target="_blank" color="primary")
  text-container(url="resources-faq.md")
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import PageMenu from "common/NiPageMenu"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-faq",
  metaInfo: { title: "Cosmos FAQ - Resources" },
  components: {
    Btn,
    Page,
    PageMenu,
    TextContainer
  }
}
</script>
