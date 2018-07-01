<template lang="pug">
page(
  :title="$t('TestnetTutorial')"
  :subtitle="$t('Learn how to build a single node')")
  div(slot="menu")
    btn(icon="chat" :value="$t('ValidatorChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
    btn(icon="chat" :value="$t('ValidatorForum')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank")
  text-container(
    url='validators-testnet.md')
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-validators-testnet",
  metaInfo: { title: "Testnet Tutorial - Validators" },
  components: {
    Btn,
    Page,
    TextContainer
  }
}
</script>
