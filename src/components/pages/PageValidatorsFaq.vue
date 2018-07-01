<template lang="pug">
page(
  :title="$t('ValidatorFAQ')"
  :subtitle="$t('Frequently asked questions and answers about Cosmos Validators.')")
  div(slot="menu")
    btn(icon="chat" :value="$t('ValidatorChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
    btn(icon="chat" :value="$t('ValidatorForum')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank")
  text-container(
    url='validators-faq.md')
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-validator-faq",
  metaInfo: { title: "FAQ - Validators" },
  components: {
    Btn,
    Page,
    TextContainer
  }
}
</script>
