<template lang="pug">
page(:title="$t('Developers')" :subtitle="$t('Learn about and contribute to the code that powers the EOS Cochain ecology.')")
  div(slot="menu"): btn(icon="chat" :value="$t('CommunityChat')" type="anchor" href="https://riot.im/app/#/group/+cosmos:matrix.org" target="_blank" color="primary")
  text-container(url="developers-index.md")
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import Part from "common/NiPart"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-developers-index",
  metaInfo: { title: "Overview - Developers" },
  components: {
    Btn,
    Page,
    Part,
    TextContainer
  }
}
</script>
